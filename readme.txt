            __________              ____  __    __
           /  __  __  \____  ____  / __ \/ /   / /
          /  / / / /  / __ \/  __\/ /_/ / /___/ /
         /  / / / /  / /_/ /  /  /  ___/  ___  /
         \_/  \/  \_/\____/\_/   \_/   \_/  /_/

  By Walkerfuz of Taurus Security(github.com/walkerfuz)
                                  Morph - Version 0.2.1
=====================================================================================

@PCanyi: Fuzz�Ĺؼ����ںõı������棬��Ч�ļ�������Լ��ȶ�����������


������ʷ
========

v0.2.1 2015/12/3
	   �Ż���Fuzzer����ı�д��ʽ ��Ϊmorph_random morph_fuzz morph_notify_href������
	   ���������������������CrashʱMorph��Ŷ�ȡ��ѭ���Ĵ���
       �Ż�����������ʱ�Ķ�WebSockets���������߼�
	   ��Readme�������˹ر�Firefox��ȫģʽ�ķ���

v0.2.0 2015/12/2
       ȫ���дΪ��̬Fuzz��� ����file:///���ش���ҳ����Fuzz
	   �����IE��Internet��IntranetȨ�޲�ͬ����Morph��ĳЩCrash���������������bug

V0.1.5 2015/11/6
       �����Subprocess.Popen����OSError WinError 1455�Ĵ���
       �����MSECExtentions v1.6.0�����Windbg�г���Can't load Library�Ĵ���

v0.1.4 �Ż�core/psutilȫ������yield������
       ������hProcess���û�йرյ�����
	   ������WebServer��404���ر�־

v0.1.3 ������t_m.isAlive�жϼ�ؽ����Ƿ����������ı�־
       �����log.txtû����������open���ļ�ʧ�ܵ��쳣��ʾ

v0.1.2 �����Process32First��Process32Next����ֵ����ͬ��Python False�������ʹ����bug
       ��while Trueѭ���޸�Ϊwhile 1
       ������ÿ�����ֺ�log�ļ���ɾ��

v0.1.1 �����threading.join��ʱ����CrashProc��Monitor���߳�û�н�����bug

v0.1.0 ������������ǩҳ����Ӧ����Fuzzѭ���������е�bug


ʹ��ǰ׼��
==========
1. ��װWindbgx86 or Windbgx64��
   ����MSECExtensions�������Windbg��winext�ļ��У�����Windbg����load msec.dll�Ƿ�ɹ���������Can't Load Library�Ĵ�������Ҫ��װVisual C++ Redistributable for Visual Studio 2008/2012��
   ע�⣺MSECExtensions1.6.0��ҪVC++2012����ʱ����֧�֡�

2. ��Windbg�����ļ����µ�cdb.exe����ΪĬ��JIT��ʱ��������
   >cdb.exe -iaec "-logo c:/log.txt -c \"!load msec.dll;!exploitable -v;\""
   ע�⣺c:/log.txt��config.py�е�Debugger�е�log��������һ��

3.���Fuzzģ����Firefox������Ҫ�رհ�ȫģʽ
  ��firefox����about:config�ҵ�toolkit.startup.max_resumed_crashes��Ĭ����3������������Ϊ-1���ɹر�Safe Mode��
  ������Ҫ��Firefoxѡ��-->��˽-->ѡ��'����¼��ʷ' �ر�Firefox����ʷ��¼����

4.����WindbgĿ¼���Դ���gflags.exe����ģ����̵�ҳ�ѵ��Թ��ܣ�����IE�������
  >Gflags.exe /i iexplore.exe +hpa

5.����Morph������Config.py�е�Ĭ�ϲ�����

6.���У�
  >morph.py --browser=IE --fuzzer=nduja.html

��ע��Ϣ
========

1. ȡ��JIT��ʱ������ָ����
	ɾ��
	x86: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\AeDebug
	��
	x64: HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Windows NT\CurrentVersion\AeDebug
	���µ�
	Debugger ��Auto��ֵ

TODO����
========

P1. ���Windbg��MSECExtensions��VC++����ʱ����������ƥ�䣩�Ϸ���

P2. Crash�ļ��д���IE11��������汾���ļ���

P3. ÿ��Fuzzer����Ϊ1���ļ���

P4. ����HttpЭ��֧�֣��Ż�FuzzЧ��
