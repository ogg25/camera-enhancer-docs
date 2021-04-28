---
layout: default-layout
title: Dynamsoft Camera Enhancer - Guide on Java(Android)
description: This is the documentation - Guide on Java(Android) page of Dynamsoft Camera Enhancer.
keywords:  Camera Enhancer, Guide on Java(Android)
needAutoGenerateSidebar: true
breadcrumbText: Android Guide draft
---

# Guide on Java(Android)

## System Requirements

- Operating system:
  - Supported OS: Android 5 or higher (Android 7 or higher recommended)
  - Supported ABI: arm64-v8a/armeabi-v7a/x86/x86_6

## Installation

1. <a href="https://download.dynamsoft.com/dce/dce-android-1.0.zip?ver=latest" target="_blank">Download Dynamsoft Camera Enhancer</a> from Dynamsoft website to get `dce-android-{version-number}.zip`. Unzip the package to find `DynamsoftCameraEnhancerAndroid.aar`. 

2. Create a new Android project in Android Studio.

3. Put the `.aar` file under the dictionary `/app/libs` in your project. 

4. Add the following code into `build.gradle(Module: app)`.

    ```Java
    repositories {
        flatDir {
            dirs 'libs'
        }
    }
    ```

5. Also in `build.gradle(Module: app)` add the reference in dependencies:

    ```Java
        implementation(name: 'DynamsoftCameraEnhancerAndroid', ext: 'aar')
    ```

6. Sync the project with gradle and after that `DynamsoftCameraEnhancerAndroid.aar` is added to your project.

## Get Started

### Create a Camera Module

This section is a guide on using Dynamsoft Camera Enhancer to create a simple camera app.

1. Create a new Android project.

2. In the new project, create a CameraView section in activity_main.xml.

    ```XML
        <com.dynamsoft.dce.CameraView
            android:id="@+id/cameraView"
            android:layout_width="match_parent"
            android:layout_height="match_parent"
            tools:layout_editor_absoluteX="25dp"
            tools:layout_editor_absoluteY="0dp" />
    ```

3. Set up for your camera in the `cameraView` section. Please add the following code in your activity for the camera. The following code is an example of setting camera view in `MainActivity`

    ```java
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
            //Initialize your license
            com.dynamsoft.dce.DMLTSConnectionParameters info = new com.dynamsoft.dce.DMLTSConnectionParameters();
            // The organization id 200001 here will grant you a public trial license good for 7 days.
            // After that, you can send an email to trial@dynamsoft.com
            // (make sure to include the keyword privateTrial in the email title)
            // to obtain a 30-day free private trial license which will also come in the form of an organization id.
            info.organizationID = "200001";
            mCamera.initLicenseFromLTS(info,new CameraLTSLicenseVerificationListener() {
                @Override
                public void LTSLicenseVerificationCallback(boolean isSuccess, Exception error) {
                    if(!isSuccess){
                        error.printStackTrace();
                    }
                }
            });
            //Turn on the camera
            mCamera.setCameraDesiredState(CameraState.CAMERA_STATE_ON);
            //Start scanning
            mCamera.startScanning();
        }
    }
    ```

4. Run the project. Now your camera module is running. If you have any questions about the program, you can view `samples` we provided in the package you download to get better understandings. Also, you can get help from our online customer service.

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
