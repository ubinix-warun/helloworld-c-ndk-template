# HelloWorld C NDK Template

This project is a template for creating Android applications (executable file) using the Native Development Kit (NDK) with C. It provides a basic structure to get started with native development on Android.

## Features

- Basic Android project setup with NDK support.
- Example C code for native functionality.

## Prerequisites

- Android Studio installed.
- Android NDK installed (can be installed via Android Studio SDK Manager).
- Basic knowledge of C and Android development.

## Getting Started

### Steps to Build and Run the Project

1. **Clone the Repository**  
   Use the following commands to clone the repository and navigate into the project directory:

   ```bash
   git clone https://github.com/yourusername/helloworld-c-ndk-template.git
   cd helloworld-c-ndk-template
   ```

2. **Build the Project**  
   Ensure that all dependencies are resolved and the project is built using the Android NDK (Native Development Kit):

   ```bash
   $NDK_PATH/ndk-build clean
   $NDK_PATH/ndk-build
   ```

   - `$NDK_PATH` should point to the directory where the Android NDK is installed.
   - `ndk-build clean` removes any previously built files to ensure a fresh build.
   - `ndk-build build` compiles the native C code and generates the necessary binaries.

3. **Run the App**  
   Deploy the compiled binary to an Android emulator or physical device and execute it:

   ```bash
   adb push libs/armeabi-v7a/helloworld /sdcard
   adb shell
   ```

   - `adb push` transfers the compiled binary (`helloworld`) to the device's `/sdcard` directory.
   - `adb shell` opens a shell session on the connected Android device.

   Inside the shell, execute the following commands:

   ```bash
   cd /data
   mv /sdcard/helloworld .
   chmod +x helloworld
   ./helloworld
   ```

   - `cd /data`: Navigate to the `/data` directory, which is writable and suitable for running binaries.
   - `mv /sdcard/helloworld .`: Move the binary from the `/sdcard` directory to `/data`.
   - `chmod +x helloworld`: Make the binary executable.
   - `./helloworld`: Run the binary, which prints `Hello, World!` to the console.

## Project Structure
- `jni/`: Contains the native C code and build configuration files.
    - `Android.mk`: Defines the build rules for the native code, specifying the source files and libraries required to build the `helloworld` native library.
    - `Application.mk`: Specifies the Application Binary Interface (ABI) and CPU architectures (e.g., `armeabi-v7a`, `arm64-v8a`) to be supported during the build process.
- `helloworld.c`: Contains the native C code that implements the core functionality of the application. This file serves as an example of how to write and integrate native code with the Android application using the NDK.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Contributing

Contributions are welcome! Feel free to open issues or submit pull requests.

## Contact

For any questions or feedback, please contact [your email or GitHub profile link].
