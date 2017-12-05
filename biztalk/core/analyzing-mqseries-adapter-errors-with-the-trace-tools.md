---
title: "トレース ツールを使用して MQSeries アダプターのエラーの分析 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Adapter Trace Utility, about Adapter Trace Utility
- Adapter Trace Utility, installing
- installing, Adapter Trace Utility
- Adapter Trace Utility, enabling
- errors, MQSeries adapters
- MQSeries adapters, Adapter Trace Utility
- Adapter Trace Utility, running
- MQSeries adapters, errors
- Adapter Trace Utility
ms.assetid: fdc73d99-3b73-491d-9b2f-7064364fefa7
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b53d1d2c0bbe19c54804b553041f8dc9ae4db20c
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="analyzing-mqseries-adapter-errors-with-the-trace-tools"></a>トレース ツールを使用して MQSeries アダプターのエラーの分析
アプリケーションの実行時に、トレース ツールを使用して、メッセージングのエラーを分析します。 MQSeries アダプタでは、アダプタと BizTalk アプリケーション (trace.cmd) 用と、MQSAgent (MQSTrace.cmd) 用の 2 つのツールを使用する必要があります。 どちらのツールでも、tracelog.exe が使用されます。 まだインストールしていない場合は、インストールしてください。  
  
 Trace.cmd と MQSTrace.cmd の両方では、オプションを設定する必要がある (**-ツール**) これらのツールが tracelog.exe ファイルを検索できるようにします。  
  
## <a name="install-the-trace-utility"></a>Trace Utility をインストールするには  
 BizTalk Adapter Trace Utility をインストールするには、次の手順を実行します。  
  
1.  Tracelog.exe ファイルをダウンロードするには、Microsoft Platform SDK ダウンロード Web サイトを参照してください。 [http://go.microsoft.com/fwlink/?LinkId=21975](http://go.microsoft.com/fwlink/?LinkId=21975)です。  
  
2.  リンクをクリックして、プラットフォーム SDK Web インストール プログラムを開始、 **x86.exe** Web ページの下部にあるファイルです。  
  
3.  インストールの種類を選択するダイアログ ボックスが表示されたら、カスタム インストール用のオプションを選択します。  
  
4.  **[Custom Installation]** ダイアログ ボックスで、利用可能な機能をすべてオフにします。  
  
5.  **[Microsoft Windows Core SDK]** 機能を展開し、 **[Tools]** 機能を展開します。  
  
6.  **[Tools (Intel 64-bit)]** 機能を選択し、 **[Will be installed on local hard drive]**をクリックします。  
  
7.  **[Next]**を 2 回クリックし、インストールを開始します。 ****  
  
8.  検索、*ドライブ*:\\*MicrosoftPlatformSDKInstallationFolder\bin*フォルダーをクリックし、Microsoft BizTalk Server のインストール フォルダーに Tracelog.exe ファイルをコピーします。 BizTalk Server のインストール フォルダには、Trace.cmd ファイルも含まれています。  
  
## <a name="enable-the-trace-utility"></a>Trace Utility を有効にするには  
 BizTalk Server で BizTalk Adapter Trace Utility を有効にするには、次の手順を実行します。  
  
1.  trace.cmd があるディレクトリに移動します。 既定の場所は、Microsoft BizTalk Server ディレクトリです。  
  
2.  次のコマンドを入力します。入力時に二重引用符で囲まれたディレクトリを、使用しているコンピュータの tracelog.exe ファイルがあるディレクトリに置き換えてください。入力後、Enter キーを押します。  
  
     **トレース - ツール"c:\Program files \microsoft sdk \bin"**  
  
3.  MQSTrace.cmd があるディレクトリに移動します。  
  
4.  次のコマンドを入力します。入力時に二重引用符で囲まれたディレクトリを、使用しているコンピュータの tracelog.exe ファイルがあるディレクトリに置き換えてください。入力後、Enter キーを押します。  
  
     **MQSTrace-ツールの"c:\Program files \microsoft sdk \bin"**  
  
## <a name="run-the-trace-utility"></a>Trace Utility を実行するには  
 BizTalk Adapter Trace Utility を実行するには、次の手順を実行します。  
  
1.  コマンド プロンプトで次のように入力します。 **trace.cmd--start-high**、ENTER キーを押します。  
  
2.  エラーが発生するシナリオを実行します。  
  
3.  コマンド プロンプトで次のように入力します。 **trace.cmd-停止**、ENTER キーを押します。  
  
4.  bts2006.bin ファイルには、トレース ツールの出力が含まれます。 分析のため、マイクロソフト製品サポート サービスに連絡してください。 詳細については、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=41645](http://go.microsoft.com/fwlink/?LinkId=41645)です。  
  
 MQSAgent Trace Utility を実行するには、次の手順を実行します。  
  
1.  コマンド プロンプトで次のように入力します。 **MQSTrace.cmd--start-high**、ENTER キーを押します。  
  
2.  エラーが発生するシナリオを実行します。  
  
3.  コマンド プロンプトで次のように入力します。 **MQSTrace.cmd-停止**です。  
  
4.  MQSAdapterTrace.bin ファイルには、トレース ツールの出力が含まれます。 分析のため、マイクロソフト製品サポート サービスに連絡してください。 詳細については、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=41645](http://go.microsoft.com/fwlink/?LinkId=41645)です。