## Eclipse환경 nRF52보드 Bluetooth예제

### 필요한 도구
  - Android phone
  - nRF52 보드
  - GNU Tool
  - GNU Make
  - GNU Core
  - Eclipse for C/C++ developer
  - nRF5x Command Line Tools

### 예제 실행 방법
  1. 새로운 프로젝트 생성
  - New > MakeFile Project with Exiting Code선택  
  ![image1][image1]
  - bluetooth 예제폴더를 설정하고 toolchain 방식을 Cross ARM GCC로 지정  
  ![image2][image2]

  2. 프로젝트에 폴더를 생성하고 MakeFile에서 참조하는 소스들을 import한다.  
  - Application폴더를 생성  
  ![image3][image3]
  - nRF_Driver폴더 생성  
   ![image4][image4]
  - Application폴더에 main.c소스를 import한다.  
   ![image5][image5]
   ![image6][image6]
  - 아래 그림과 같이 실행하는 Bluetooth예제 경로를 지정하고 main.c파일 체크  
   ![image7][image7]
  - 같은 방법으로 nRF_Driver폴더에 component를 import한다.  
   ![image8][image8]

  3. Build Target 실행 파일을 생성한다.  
  - Build Target에서 New Build Target 버튼 선택  
   ![image9][image9]
  - Build Target생성 제목을 nrf52832_xxaa flash로 생성  
   ![image10][image10]
  - 같은 방법으로 nrf52382_xxaa flash_softdevice 생성  
   ![image11][image11]
  
  4. 프로젝트 속성을 수정한다.
  -  프로젝트를 우클릭하여 C/C++ Build > Build Settings > Build Command에서 make VERBOSE=1로 수정한다.  
   ![image12][image12]
  -  C/C++ General > Preprocessor Include Paths > Provider > CDT GCC Build Output Parser > Compliler command pattern항목에 Command 패턴을 (.*gcc)|(.*[gc]\+\+)로 수정한다  
   ![image13][image13]
  -  C/C++ General > Preprocessor Include Paths > Provider > CDT GCC Build-in Compiler Settings Cross ARM > Command to get cmpiler specs항목에 ${Command}을 arm-none-eabi-gcc로 수정한다.    
   ![image14][image14]
  - MakeFile에서 -Wall -Werror -O3 -g3을 -Wall -Werror -O0 -g3으로 수정한다.  
   ![image15][image15]

   5. 프로젝트를 실행한다.
   - nrf52832_xxaa flash_softdevice를 더블클릭  
   ![image16][image16]
   - nrf52832_xxaa flash를 더블클릭하여 실행한다.  
   ![image17][image17]


[image1]:images/BluetoothBlinkyExample1.jpg
[image2]:images/BluetoothBlinkyExample2.jpg
[image3]:images/BluetoothBlinkyExample3.jpg
[image4]:images/BluetoothBlinkyExample4.jpg
[image5]:images/BluetoothBlinkyExample5.jpg
[image6]:images/BluetoothBlinkyExample6.jpg
[image7]:images/BluetoothBlinkyExample7.jpg
[image8]:images/BluetoothBlinkyExample8.jpg
[image9]:images/BluetoothBlinkyExample9.jpg
[image10]:images/BluetoothBlinkyExample10.jpg
[image11]:images/BluetoothBlinkyExample11.jpg
[image12]:images/BluetoothBlinkyExample12.jpg
[image13]:images/BluetoothBlinkyExample13.jpg
[image14]:images/BluetoothBlinkyExample14.jpg
[image15]:images/BluetoothBlinkyExample15.jpg
[image16]:images/BluetoothBlinkyExample16.jpg
[image17]:images/BluetoothBlinkyExample17.jpg





 







