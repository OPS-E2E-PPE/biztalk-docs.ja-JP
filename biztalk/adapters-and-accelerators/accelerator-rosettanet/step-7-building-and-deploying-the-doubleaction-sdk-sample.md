---
title: '手順 7: ビルドと DoubleAction SDK サンプルの展開 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- double action tutorial, building solutions
- deploying, solutions
- building solutions
- double action tutorial, deploying solutions
ms.assetid: f67f8aee-1004-48ee-a6fd-881097382888
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c4664210cf4911f180b44b470db01aa2948531f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998675"
---
# <a name="step-7-building-and-deploying-the-doubleaction-sdk-sample"></a>手順 7: ビルドと DoubleAction SDK サンプルの展開
DoubleAction.odx サンプルでは、オーケストレーションを実装し、ダブル アクションの PIP (Partner Interface Process) である 0C2、0C4、3A2、および 3A40 に対する応答を自動的に生成する方法を示します。 このサンプル プロジェクトを拡張し、さらに多くのダブルアクション PIP をサポートすることもできます。  
  
 このサンプルを使用すると、Fabrikam が 4 つの PIP のいずれかを使用して要求を行ったときに、自動的に Fabrikam に応答が送信されます。  
  
### <a name="to-build-and-initialize-the-doubleaction-sample"></a>DoubleAction サンプルをビルドして初期化するには  
  
1. Contoso コンピューターのコマンド プロンプト ウィンドウで、次のフォルダーに移動します。   
   *\<ドライブ\>*: \Program Files\\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\pipautomation\doubleaction\\します。  
  
   > [!NOTE]
   >  セットアップ プログラムを実行する前に、メモ帳で DoubleAction.sql ファイル (上のフォルダーに置かれています) を開きます。 **ファイル** メニューのをクリックして**付けて**します。 **エンコード**ボックスで、 **ANSI**クリックしてドロップダウン リストから**保存**します。 をクリックして**はい**既存のファイルを上書きします。  
  
2. BizTalk Server のインストールが SQL Server 2008 R2 または 2008 SP1 を実行している場合は、同じフォルダーに setupx64.bat を実行します。 バッチ ファイルによって、次の処理が実行されます。  
  
   - BTARNDATA データベースに、MessagesToLOB テーブルからアクション メッセージを取得する SQL ストアド プロシージャ (`PipAutomationGetAction`) を作成します。  
  
   - HeaderHelper .NET プロジェクトをコンパイルし、グローバル アセンブリ キャッシュにアセンブリを登録します。  
  
   - [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] SQL 受信ポート (MessagesToLOB_Receive_Port) を作成し、バインドします。  
  
   - 受信場所 (MessagesToLOB_Receive_Location) を有効にします。  
  
   - コンパイルし、ダブル アクション PIPAutomation オーケストレーション (DoubleAction.odx) を展開します。  
  
   - [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] オーケストレーションをバインドして、開始します。  
  
     > [!NOTE]
     >  コンパイル中に警告がいくつか表示されます。 これらの警告は無視してかまいません。  
  
     > [!NOTE]
     >  DoubleAction.odx にバインドされていることを確認**MessagesToLOB_Receive_Port**オーケストレーションが開始されているとします。  
  
3. BizTalk Server 管理コンソールで、展開、 **BizTalk グループ**、**アプリケーション**、および**BizTalk アプリケーション 1**ノード。 をクリックして、**オーケストレーション**ノード。 右クリックし、 **DoubleAction**オーケストレーション、およびクリック**プロパティ**します。 [プロパティ] ダイアログ ボックスで、**バインド**ノード、および設定して、**ホスト**に **[biztalkserverapplication]** 設定と、**受信ポート**に **[messagetolob_receiveport]** します。 **[OK]** をクリックします。 右クリックし、 **DoubleAction**オーケストレーション、およびクリック**開始**します。  
  
## <a name="see-also"></a>参照  
 [Fabrikam ソリューションの作成と構成](../../adapters-and-accelerators/accelerator-rosettanet/creating-and-configuring-the-fabrikam-solution.md)