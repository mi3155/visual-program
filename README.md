# visual-program
## 자기소개서
* 학번 : 20151257
* 이름 : 황지환
* 취미 : 게임, 노래듣기

1

새 프로젝트 만들기 - mfc 를 입력 및 클릭

프로젝트이름을 자신이 원하는 제목으로 바꿔준다

애플리케이션 종류 - 대화 상자 기반으로 바꾼다.

대화상자 편집기를 열어서

button 하나를 가져오고

Eidt Control에 들어가서 입력할 2개의 상자와 결과값을 표출할 상자하나를 가져온다.

button을 한번클릭한후 Caption으로 들어가 + 로 바꿔준다

그후 +를 더블클릭후 
	그 자리에 
int a = GetDlgItemInt(IDC_EDIT1);
	int b = GetDlgItemInt(IDC_EDIT2);
	int c = a + b;
	SetDlgItemInt(IDC_EDIT3, c);
이것을 추가해주면 끝.

2

첫번째 계산기에서 이제 제목을 추가해주는 역할을 만들건데

아까와 같이  button을 하나 만들어주고,

EditControl을 통하여 입력할 상자를 하나 만들어줍니다.

그후

속성 4번째 메세지에 add on mousemove를 추가하라

그리고난뒤


int size=1;
CPoint pnt;
void CPen71Dlg::OnMouseMove(UINT nFlags, CPoint point)
{
	if (nFlags == MK_LBUTTON) {
		CClientDC dc(this);
		CPen pen(PS_SOLID, size, RGB(255, 0, 0));
		dc.SelectObject(&pen);
		dc.MoveTo(pnt);
		dc.LineTo(point);
	}
	// TODO: 여기에 메시지 처리기 코드를 추가 및/또는 기본값을 호출합니다.
	pnt = point;
	CDialogEx::OnMouseMove(nFlags, point);
}
를 입력
그리고 대화상자 편집기에서 Slide Control을 만들어준다

Slide Control에서 속성에 들어가서
변수 값을 m_Slider로 바꾼뒤
Slide Control을 더블클릭한 후

void CPen71Dlg::OnNMCustomdrawSlider1(NMHDR* pNMHDR, LRESULT* pResult)
{
	LPNMCUSTOMDRAW pNMCD = reinterpret_cast<LPNMCUSTOMDRAW>(pNMHDR);
	size = m_Slider.GetPos();
	// TODO: 여기에 컨트롤 알림 처리기 코드를 추가합니다.
	*pResult = 0;
}




버튼2를 더블클릭하여
그자리에다가

CTring m;
GetDlgItemText(IDC_EDIT4,m);
SetWindowText(m);
을 복사해서 붙어줍니다.

### 소감 
* 다 아는 줄 알았지만, 다시 과제를 하려고 하나하나 해보니 모르는 것 투성이였고, 다시 보고, 뭐가 잘못 되었는지 찾으면서
* 어느 부분에서 실수했는지 알수 있었고, 지금까지 했던 것을 다시 제것으로 만들수 있었던 계기가 되었습니다.
* 다시 하다보니 visual programming에 대한 흥미와 자신감 또한 올릴수있는 계기가 된 것 같습니다. 감사합니다.
