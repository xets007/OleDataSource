[20200719-08:30]
OleDataSource��Ŀ����
������а崫�����ݹ�����ʵ�ֻص���COM���Լ����������ࡣ

��β��ԣ�
���к����һ���հ״��ڣ������������->�����ڡ��˵������ᵯ�����ڶԻ���
���ǽ�����test.txt�ļ���·����COM����д����а塣
Ȼ�����������Ҽ�ճ�����ɡ�

��Щ����ļ�����Ҫ��
Ϊ�˽ṹ����������˺ܶ��࣬���Ƕ������ò�����
����Ҫ���У�
Usage.cpp : 
	HGLOBAL PutIntoClipboard(const TCHAR* path)

CMyOleDataSource.cpp : 
	BOOL CMyOleDataSource::OnRenderData(LPFORMATETC lpFormatEtc, LPSTGMEDIUM lpStgMedium)

CMyOleStream.cpp:
	HRESULT __stdcall CMyOleStream::Read(void* pv, ULONG cb, ULONG* pcbRead)
	HRESULT __stdcall CMyOleStream::Seek(LARGE_INTEGER dlibMove, DWORD dwOrigin, ULARGE_INTEGER* plibNewPosition)

������кθĶ���

ԭ���ķ���������OnRenderDataFile�д�����һ���ڴ湲���ļ�������С�ļ����Զ�
�����ڴ���Ȼ��һ��д�������ǶԴ��ļ�������������
���ڵķ����ǣ���OnRenderData�з���һ��IStream��������÷�������explorer����
���÷��������IStream::Read�����Seek����ļ����ȣ���Ҳ������OnRenderData
��һ�λص�֮�󣬶���IStream::Read���ж��λص���

��ʱ����CMyOleStream���Լ�ʵ������ص����ṩ��Ҫ�����ݼ��ɡ�
��Ϳ���ʵ�ֱߴ�����ṩ���ݸ����÷���Ч����

��Ҫע�������:
������Ϣѭ��֮ǰҪ�ȳ�ʼ��OLE

    // Initialize COM and OLE
    if (OleInitialize(0) != S_OK)
        return 0;
		
��֮��Ҫж��OLE
    // Cleanup
    OleUninitialize();

���WinLoop.cpp
