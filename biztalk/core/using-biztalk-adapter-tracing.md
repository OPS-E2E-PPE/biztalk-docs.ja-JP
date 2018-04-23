---
title: BizTalk アダプターのトレースを使用して |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Adapter Trace Utility, installing
- installing, Adapter Trace Utility
- Adapter Trace Utility, enabling
- Adapter Trace Utility, running
- enabling, Adapter Trace Utility
ms.assetid: ddc6b2c7-9dee-43c1-950b-8fd580bfcb26
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d1e14234363ace4b953fa4766a97502753572e6f
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2018
---
# <a name="using-biztalk-adapter-tracing"></a>BizTalk アダプターのトレースの使用
ここでは、Trace Log tool (トレース ログ ツール) をインストールする方法、および BizTalk アダプターのトレースを可能にする方法について説明します。  
  
## <a name="install-the-trace-log-tool"></a>トレース ログ ツールのインストール  
  
#### <a name="to-install-the-trace-log-tool-tracelogexe"></a>トレース ログ ツール (tracelog.exe) をインストールするには  
  
1.  トレース ログ ツールを [Microsoft® Windows® Software Development Kit Update for Windows Vista](http://go.microsoft.com/fwlink/?LinkId=128279) Web サイトからダウンロードします。  
  
    > [!NOTE]
    >  [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] を実行している場合でも、このバージョン (6.0) の SDK をインストールしてください。 インストールする場合、 **Windows SDK の Windows Server 2008 および .NET Framework 3.5** バージョン (v です。 6.1)、トレース ログ ツールはインストールされません。  
  
2.  Web ページ下部にある **PSDK-x86.exe** ファイルのリンクをクリックして、 **Microsoft® Windows® Software Development Kit Update for Windows Vista** Web インストール プログラムを起動します。  
  
    > [!NOTE]
    >  64 ビット版の Windows を使用している場合は、お使いのシステム用の正しいファイルを選択してダウンロードしてください。  
  
3.  **[Select an Installation Type]** ダイアログ ボックスで、 **[Custom]** インストールを選択し、 **[Next]**をクリックします。  
  
4.  既定のインストール先をそのまま使用し、 **[Next]**をクリックします。  
  
5.  **[Custom Installation]** ダイアログ ボックスで、利用可能な機能をすべてオフにします。  
  
6.  **[Microsoft Windows Core SDK]** 機能を展開し、 **[Tools]** 機能を展開します。  
  
7.  **[Tools (Intel 64-bit)]** 機能を選択し、 **[Will be installed on local hard drive]**をクリックします。  
  
8.  **次へ**をクリックし、**次へ**をクリックしてインストールを開始します。  
  
    > [!NOTE]
    >  **Microsoft® Windows® Software Development Kit Update for Windows Vista** のインストール後、トレース ログ ツールと同時にインストールするよう選択した機能によっては、再起動を求められることがあります。 これは、 **Microsoft® Windows® Software Development Kit Update for Windows Vista** の特定のコンポーネントが、再起動するまで正常に機能しないためです。 トレース ログ ツールを使用するために再起動する必要はありません。  
  
## <a name="enable-biztalk-adapter-tracing-with-tracecmd"></a>trace.cmd を使用した BizTalk アダプターのトレースの有効化  
  
#### <a name="to-enable-biztalk-adapter-tracing"></a>BizTalk アダプターのトレースを有効化するには  
  
1.  コマンド プロンプトでは、BizTalk Server がインストールされているディレクトリに、現在のディレクトリを変更します。 既定では、BizTalk Server がインストールされている、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]ディレクトリ。  インストール パスは、Windows および BizTalk Server の 64 ビット バージョンを使用して場合[!INCLUDE[btsBizTalkServerPathx64](../includes/btsbiztalkserverpathx64-md.md)]です。  
  
2.  次のコマンドを入力し、Enter キーを押します。  
  
     **trace-tools「トレース ログ ツールのパス」ツール**  
  
     既定では、トレース ログ ツール (tracelog.exe) は **C:\Program Files\Microsoft SDKs\Windows\v6.0\Bin** ディレクトリにあります。 64 ビット版の Windows を使用している場合、トレース ログ ツールは **C:\Program Files (x86)\Microsoft SDKs\Windows\v6.0\Bin**.にあります。  トレース ログ ツールのパスは二重引用符で囲む必要があります。  
  
     たとえば、次のコマンドを入力し、ENTER キーを押します。  
  
     **trace-tools"C:\Program files \microsoft SDKs\Windows\v6.0\Bin"ツール**  
  
    > [!NOTE]
    >  **-tools** スイッチは、Trace.cmd ファイルに Tracelog.exe ファイルの場所を示します。  
    >   
    >  コマンドが正常に実行された場合は、次のように出力されます。  
    >   
    >  **2.0 - 管理 BizTalk 2006 リリース ビット トレースをトレースします。**  
    >   
    >  **設定を"C:\Program files \microsoft SDKs\Windows\v6.0\Bin"TRACE_TOOL_SEARCH_PATH**  
  
## <a name="capture-trace-output-with-tracecmd"></a>trace.cmd を使用したトレース出力の取得  
  
#### <a name="to-capture-trace-output"></a>トレース出力を取得するには  
  
1.  コマンド プロンプトでは、BizTalk Server がインストールされているディレクトリに、現在のディレクトリを変更します。  
  
2.  コマンド プロンプトで次のコマンドを入力し、Enter キーを押します。  
  
     **トレースの開始**  
  
3.  トレース出力を取得するシナリオを再現します。  
  
4.  コマンド プロンプトで次のコマンドを入力し、Enter キーを押します。  
  
     **トレースの停止**  
  
5.  という名前のバイナリ ファイル、トレースを停止した後**Btstrace.bin** 、フォルダーに生成された場所[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]がインストールされています。  
  
6.  分析のためにマイクロソフト製品サポート サービスに **Btstrace.bin** ファイルを送信します。  
  
## <a name="see-also"></a>参照  
 [アダプターを使用します。](../core/using-adapters.md)   
 [Windows SharePoint Services アダプターのトラブルシューティング](../core/troubleshooting-the-windows-sharepoint-services-adapter.md)