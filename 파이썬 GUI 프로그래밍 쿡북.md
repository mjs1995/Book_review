# 서평
- ![제목 없는 디자인 (2)](https://github.com/mjs1995/Book_review/assets/47103479/b66fb344-2143-42fd-b92b-5bf9857f0508)

# 파이썬 GUI Programming & widget
- tkinter 모듈을 이용하면 파이썬에서 손쉽게 GUI 프로그래밍을 할 수 있음 
- widget은 버튼, 텍스트박스, 레이블 등을 말하며 GUI 핵심요소
- ```python
	import tkinter
	win = tkinter.Tk()
	lbl = tkinter.Label(win, text= 'python')
	lbl.pack()
	```
- widget의 배치 & 꾸미기
  - tkinter 모듈을 이용하면 파이썬에서 손쉽게 GUI 프로그래밍을 할 수 있음
  - tkinter를 사용하면 import 한 후, 창과 위젯을 배치함
  - widget은 버튼, 텍스트박스, 레이블 등을 말하며 GUI 핵심요소
  - tkinter의 filedialog, colorchooser 등을 사용하면 파일 선택이나 컬러선택 다이얼로그를 손쉽게 구현할 수 있음
    - ```python
      from tkinter import colorchooser
      c = colorchooser.askcolor()
      ```
- 제어변수 활용하기
  - 제어변수는 위젯과 연결되어 위젯 고유의 값을 반영하기 위한 특수 객체
  - 제어변수의 type은 IntVar(), StringVar(), BooleanVar(), DoubleVar() 등이 있음
  - 제어변수의 set() 메서드나 get() 메서드를 사용하여 위젯에 값을 넣거나 조회할 수 있음 
- widget 처리 고급기법
  - 제어변수의 trace() 메서드를 이용하면 위젯의 값을 추적할 수 있음

# 이벤트 핸들링
- 이벤트 프로그래밍을 활용하면 키보드나 마우스 등의 상태 변화에 따라 세밀한 처리가 가능함
- 이벤트 프로그래밍은 크게 두 개의 구조를 형성함
  - 이벤트 발생시 처리할 문장 정의하기(이벤트 핸들러)
    - ```python
      def press_handler(e):
        print('press')
      ```
  - 이벤트 바인딩하기
    - ```python
      lbl.bind('<Key>',press_handler)
      ```
- event_add() 메서드를 사용하면 미리정의되어 있는 이벤트 외에도 사용자 정의이벤트를 추가할 수 있음
  - ```python
    win.event_add('<<Myevent>>', '<Button-1>', '<Return>')
    btn.bind('<<Myevent>>', evt_handle)
    ```
- 키보드 & 마우스 이벤트
  - 키보드나 마우스 이벤트 처리기에는 키문자값, 마우스 위치, 마우스 버튼 등 다양한 데이터가 전달됨     
- ```python
  # 위젯을 적절한 크기로 구성하여 원하는 위치에 배치하는 코드
  lbl1 = Label(win, padx = 20, text = '이 름:')
  lbl1.grid(row=0, column=0, sticky='nw')

  # 위의 레이블 값을 변경하는 코드
  lbl1.config(text='성 명') 
  ```
- pandas는 데이터를 조작하고 분석할 수 있는 도구
- 데이터를 테이블 구조로 다루며, 데이터 연산, 집계, 병합 등 다양한 메서드를 제공함 
