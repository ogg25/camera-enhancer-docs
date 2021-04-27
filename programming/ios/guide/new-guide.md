---
layout: default-layout
title: Dynamsoft Camera Enhancer - Guide on Objective-C & Swift
description: This is the documentation - Guide on Objective-C & Swift page of Dynamsoft Camera Enhancer.
keywords:  Camera Enhancer, Guide on Objective-C & Swift
needAutoGenerateSidebar: true
breadcrumbText: iOS Guide
---

# Guide on Objective-C & Swift

## System Requirements

- Operating systems:
  - macOS 10.11 and above.
  - iOS 9.0 and above.
- Environment: Xcode 7.1 - 11.5 and above.
- Recommended: macOS 10.15.4+, Xcode 11.5+, iOS 11+

## Installation

1. <a href="https://download.dynamsoft.com/dce/dce-ios-1.0.zip?ver=latest" target="_blank">Download Dynamsoft Camera Enhancer</a> from Dynamsoft website to get `dce-android-{version-number}.zip`. Unzip the package and find DynamsoftCameraEnhancer.framework. 

2. Create a new Objective-C or Swift project.

3. Add DynamsoftCameraEnhancer.framework in your Xcode project.

4. Import Dynamsoft Camera Enhancer

Objective-C:

```objectivec
#import <DynamsoftCameraEnhancer/DynamsoftCameraEnhancer.h>
```

Swift:

```Swift
import DynamsoftCameraEnhancer
```

## Get Started

### Create a Camera Module

In this section, you will be guided on using Dynamsoft Camera Enhancer to create a simple camera app with video frames filter function.

If you have completed the installation of DCE, you can add the following code to your viewController to set up your camera module.

Objective-C

```objectivec
#import <DynamsoftCameraEnhancer/DynamsoftCameraEnhancer.h>

@interface ViewController ()
@end
@implementation ViewController

- (void)viewDidLoad {
    [super viewDidLoad];
    dceView = [DCECaptureView captureWithFrame:self.view.bounds];
    //Initialize license from LTS
    iDMLTSConnectionParameters* dcePara = [[iDMLTSConnectionParameters alloc] init];
    dcePara.organizationID = @"Your organizationID";
    dce = [[DynamsoftCameraEnhancer alloc] initLicenseFromLTS:dcePara view:dceview verificationDelegate:self];
    [dce setCameraDesiredState:DCEnhancerStateOn];
}
```

Swift:

```Swift
import DynamsoftCameraEnhancer

class ViewController: UIViewController {
    var dce:DynamsoftCameraEnhancer! = nil
    var dceView:DCECaptureView! = nil
    override func viewDidLoad() {
        super.viewDidLoad()
        // Do any additional setup after loading the view.
        dce.setCameraDesiredState(.CAMERA_STATE_ON)
        dce.isEnable = true
    }
    func configurationDCE() {
        dceDate = NSDate()
        dceView = DCECaptureView.init(view: self.view.bounds)
        dceView.addOverlay(color, fill: color)
        self.view.insertSubview(dceView, belowSubview: displayView)
        //Setup license
        let lts = iCameraLTSConnectionParameters()
        lts.organizationID = "Your organizationID"
        dce = DynamsoftCameraEnhancer.init(licenseFromLTS: lts, view: dceView, verificationDelegate: self)
        dce.setCameraDesiredState(.CAMERA_STATE_ON)
    }
}
```

### Extend the camera module with DCE functions

This is a template for users to add DCE camera settings into the newly built camera module.

```Java
    import com.dynamsoft.dce.CameraEnhancer;
    import com.dynamsoft.dce.CameraEnhancerException;
    import com.dynamsoft.dce.CameraState;
    import com.dynamsoft.dce.CameraView;
    import com.dynamsoft.dce.DMLTSConnectionParameters;
    import com.dynamsoft.dce.CameraLTSLicenseVerificationListener;
    public class MainActivity extends AppCompatActivity {
        CameraEnhancer mCamera;
        CameraView cameraView;
        @Override
        protected void onCreate(Bundle savedInstanceState) {
            super.onCreate(savedInstanceState);    
            setContentView(R.layout.activity_main);
            cameraView = findViewById(R.id.cameraView);
            mCamera = new CameraEnhancer(MainActivity.this);
            mCamera.addCameraView(cameraView);
            com.dynamsoft.dce.DMLTSConnectionParameters info = new com.dynamsoft.dce.DMLTSConnectionParameters();
            info.organizationID = "200001";
            mCamera.initLicenseFromLTS(info,new CameraLTSLicenseVerificationListener() {
                @Override
                public void LTSLicenseVerificationCallback(boolean isSuccess, Exception error) {
                    if(!isSuccess){
                        error.printStackTrace();
                    }
                }
            });
            mCamera.setCameraDesiredState(CameraState.CAMERA_STATE_ON);
            mCamera.startScanning();
            //**************The Following parts are newly added*******************
            //Make device level evaluation on current device
            //User can set parameters for device level evaluation via API `setAutoModeLevelParam`         
            int level = mCameraEnhancer.getDeviceLevel();
            boolean frame_filter = true;
            boolean auto_focus = true;
            if (level == 2) {
                //Disable both auto focus and frame filter on high level device
                frame_filter = false;
                auto_focus = false;
            }else if (level == 1) {
                //Disable auto focus on mid level devices
                auto_focus = false;
            }
            mCameraEnhancer.enableDCEAutoFocus(auto_focus);
            mCameraEnhancer.enableFrameFilter(frame_filter);
            //Enable sensor control & fast mode
            mCameraEnhancer.enableSensorControl(true);        
            mCameraEnhancer.enableFastMode(true);
        }
    }
```

Run the project, now some DCE functions have been added to the camera module.

### Add decoder to the camera module

This section is the guide for users to add a video stream decoder in the camera module. In this section, Dynamsoft Barcode Reader (DBR) will support decoding works.

1. Add a new text view for the camera module. In the text view, there will be decode results if the project is running successfully.

    ```xml
        <com.dynamsoft.dce.CameraView
        android:id="@+id/cameraView"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        tools:layout_editor_absoluteX="25dp"
        tools:layout_editor_absoluteY="0dp" />
        <!--Add this TextView-->
        <TextView
            android:id="@+id/tv_res"
            android:layout_width="match_parent"
            android:layout_height="200dp"
            android:layout_marginTop="430dp"
            android:textSize="16sp"
            android:gravity="center"
            android:scrollbars="vertical"
            android:textColor="@color/white"
            android:visibility="visible"/>
        <!---->
    ```

2. Add the following code to the project in the main activity:

    ```Java
        import com.dynamsoft.dbr.BarcodeReader;
        import com.dynamsoft.dbr.BarcodeReaderException;
        import com.dynamsoft.dbr.DBRLTSLicenseVerificationListener;
        import com.dynamsoft.dbr.DCESettingParameters;
        import com.dynamsoft.dbr.TextResultCallback;
        import com.dynamsoft.dbr.TextResult;
        import com.dynamsoft.dce.CameraEnhancer;
        import com.dynamsoft.dce.CameraLTSLicenseVerificationListener;
        import com.dynamsoft.dce.CameraView;

        public class MainActivity extends AppCompatActivity {
            CameraView cameraView;            
            CameraEnhancer mCameraEnhancer;
            //************Newly added code***************
            TextResultCallback mTextResultCallback;
            BarcodeReader reader;
            TextView tvRes;
            //*******************************************
            @Override
            protected void onCreate(Bundle savedInstanceState) {
                super.onCreate(savedInstanceState);
                setContentView(R.layout.activity_main);
                cameraView = findViewById(R.id.cameraView);
                
                //**This line is newly added**
                tvRes = findViewById(R.id.tv_res);
                //****************************
                mCameraEnhancer = new CameraEnhancer(MainActivity.this);
                mCameraEnhancer.addCameraView(cameraView);
                //Initialize DCE from License Tracking Server
                com.dynamsoft.dce.DMLTSConnectionParameters info = new com.dynamsoft.dce.DMLTSConnectionParameters();
                info.organizationID = "200001";
                mCameraEnhancer.initLicenseFromLTS(info,new CameraLTSLicenseVerificationListener() {
                    @Override
                    public void LTSLicenseVerificationCallback(boolean isSuccess, Exception error) {
                        if(!isSuccess){ error.printStackTrace(); }
                    }
                });
                mCamera.setCameraDesiredState(CameraState.CAMERA_STATE_ON);
                mCamera.startScanning();

                //**************The Following parts are newly added*******************
                //Make device level evaluation on current device
                //User can set parameters for device level evaluation via API `setAutoModeLevelParam`         
                int level = mCameraEnhancer.getDeviceLevel();
                boolean frame_filter = true;
                boolean auto_focus = true;
                if (level == 2) {
                    //Disable both auto focus and frame filter on high level device
                    frame_filter = false;
                    auto_focus = false;
                }else if (level == 1) {
                    //Disable auto focus on mid level devices
                    auto_focus = false;
                }
                mCameraEnhancer.enableDCEAutoFocus(auto_focus);
                mCameraEnhancer.enableFrameFilter(frame_filter);
                //Enable sensor control & fast mode
                mCameraEnhancer.enableSensorControl(true);        
                mCameraEnhancer.enableFastMode(true);

                //******************The following parts are newly added******************************
                //Initialize Dynamsoft Barcode Reader from License Tracking Server
                try {
                    reader = new BarcodeReader();
                    com.dynamsoft.dbr.DMLTSConnectionParameters parameters = new com.dynamsoft.dbr.DMLTSConnectionParameters();
                    parameters.organizationID = "200001";
                    reader.initLicenseFromLTS(parameters, new DBRLTSLicenseVerificationListener() {
                        @Override
                        public void LTSLicenseVerificationCallback(boolean b, Exception e) {
                            if (!b) { e.printStackTrace(); }
                        }
                    });
                } catch (BarcodeReaderException e) {
                    e.printStackTrace();
                }
                //Get the text result from Dynamsoft Barcode Reader
                mTextResultCallback = new TextResultCallback() {
                    @Override
                    public void textResultCallback(int i, TextResult[] textResults, Object o) {
                        showResult(textResults);
                    }
                };                
                //Set DCE setting parameters in Dynamsoft Barcode Reader
                DCESettingParameters dceSettingParameters = new DCESettingParameters();
                dceSettingParameters._cameraInstance = mCameraEnhancer;
                dceSettingParameters._textResultCallback = mTextResultCallback;
                //Instantiate DCE, send result and immediate result call back to Dynamsoft Barcode Reader
                reader.SetCameraEnhancerParam(dceSettingParameters);
            }
            //Start DCE on resume
            @Override
            public void onResume() {
                reader.StartCameraEnhancer();
                super.onResume();
            }
            //Stop DCE on pause
            @Override
            public void onPause() {
                reader.StopCameraEnhancer();
                super.onPause();
            }
            //This is the function for displaying decode result on the screen
            private void showResult(TextResult[] results) {
                if (results != null && results.length > 0) {
                    String strRes = "";
                    for (int i = 0; i < results.length; i++)
                        strRes += results[i].barcodeText + "\n\n";
                    tvRes.setText(strRes);
                }
            }
        }
    ```

3. Run the project, now a simple decode app has been built via Dynamsoft Camera Enhancer and Dynamsoft Barcode Reader.
