# MLX90640 / MLX90641 Thermal Viewer

Raspberry Pi에서 I²C로 열화상 센서 데이터를 읽고 OpenCV로 표시하는 Python 예제입니다. MLX90640의 32×24 또는 MLX90641의 16×12 온도 배열을 영상으로 변환합니다.

## 처리 흐름

센서 프레임 읽기 → NumPy 배열 변환 → 정규화 → 확대 및 컬러 표시

[thermal_image.py](thermal_image.py)의 `CHIP_TYPE`으로 센서를 선택합니다. 화면 확대는 원본 센서 해상도를 높이는 것이 아니며, 프레임별 정규화 색상은 고정된 절대 온도 눈금과 구분해야 합니다.

## 실행 준비

- Raspberry Pi의 I²C 활성화와 센서 연결
- Python, `seeed_mlx9064x`, NumPy, OpenCV
- [requirements.txt](requirements.txt)의 의존성과 센서 드라이버 설치 확인

```bash
python thermal_image.py
```

OpenCV 창을 표시할 수 있는 환경이 필요합니다. C++ 수집 구현은 [thermal_mlx90640_cpp](https://github.com/lsirikh/thermal_mlx90640_cpp)에 있습니다.

<details>
<summary>기존 개발 기록 및 참고 자료</summary>

## MLX90640 Thermal Image Sensor for RPi4

### Developer : GH
### E-Mail : lsirikh@naver.com
### Release : 2024-09-24

<hr>

#### Using MLX90640 with RPI4 via I2C for Visualization 

You can acquire data from MLX90640 through I2C on RPI4.  

1. python based project with seeed_mlx9064x lib.
2. Visualization using OpenCV with colored mapping.  

Sample image is located at `/pics/example.png`.

![Sample Image](./pics/example1.jpg)
![Sample Image](./pics/example2.jpg)

</details>
