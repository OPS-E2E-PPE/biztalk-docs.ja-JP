---
title: '手順 7: ビルドと DoubleAction SDK サンプルの展開 |Microsoft ドキュメント'
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
ms.openlocfilehash: 6d9ebd9fe513e302c5bee83e902ed0d275c8785b
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26005379"
---
# <a name="step-7-building-and-deploying-the-doubleaction-sdk-sample"></a>手順 7: ビルドと DoubleAction SDK サンプルの展開
DoubleAction.odx サンプルでは、オーケストレーションを実装し、ダブル アクションの PIP (Partner Interface Process) である 0C2、0C4、3A2、および 3A40 に対する応答を自動的に生成する方法を示します。 このサンプル プロジェクトを拡張し、さらに多くのダブルアクション PIP をサポートすることもできます。  
  
 このサンプルを使用すると、Fabrikam が 4 つの PIP のいずれかを使用して要求を行ったときに、自動的に Fabrikam に応答が送信されます。  
  
### <a name="to-build-and-initialize-the-doubleaction-sample"></a>DoubleAction サンプルをビルドして初期化するには  
  
1.  Contoso コンピューターのコマンド プロンプト ウィンドウで、次のフォルダーに移動します。   
    *\<ドライブ\>*: \Program Files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk\<バージョン\>Accelerator for rosettanet \sdk\pipautomation\doubleaction\\です。  
  
    > [!NOTE]
    >  セットアップ プログラムを実行する前に、メモ帳で DoubleAction.sql ファイル (上のフォルダーに置かれています) を開きます。 **ファイル** メニューのをクリックして**名前を付けて保存**です。 **エンコード**ボックスで、 **ANSI**クリックしてドロップダウン リストから**保存**です。 をクリックして**はい**既存のファイルを上書きします。  
  
2.  BizTalk Server のインストールが SQL Server 2008 R2 または 2008 SP1 を実行している場合は、同じフォルダーに setupx64.bat を実行します。 バッチ ファイルによって、次の処理が実行されます。  
  
    -   BTARNDATA データベースに、MessagesToLOB テーブルからアクション メッセージを取得する SQL ストアド プロシージャ (`PipAutomationGetAction`) を作成します。  
  
    -   HeaderHelper .NET プロジェクトをコンパイルし、グローバル アセンブリ キャッシュにアセンブリを登録します。  
  
    -   [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] SQL 受信ポート (MessagesToLOB_Receive_Port) を作成し、バインドします。  
  
    -   受信場所 (MessagesToLOB_Receive_Location) を有効にします。  
  
    -   コンパイルし、ダブル アクション PIPAutomation オーケストレーション (DoubleAction.odx) を展開します。  
  
    -   [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] オーケストレーションをバインドして、開始します。  
  
        > [!NOTE]
        >  コンパイル中に警告がいくつか表示されます。 これらの警告は無視してかまいません。  
  
        > [!NOTE]
        >  DoubleAction.odx にバインドされていることを確認**MessagesToLOB_Receive_Port**オーケストレーションが開始されているとします。  
  
3.  BizTalk Server 管理コンソールで、展開、 **BizTalk グループ**、**アプリケーション**、および**BizTalk アプリケーション 1**ノード。 クリックして、**オーケストレーション**ノード。 右クリックし、 **DoubleAction**オーケストレーション、およびクリック**プロパティ**です。 [プロパティ] ダイアログ ボックス、**バインド**ノードを展開し、セット、**ホスト**に**BizTalkServerApplication**設定と、**受信ポート**に **[messagetolob_receiveport]** です。 **[OK]** をクリックします。 右クリックし、 **DoubleAction**オーケストレーション、およびクリック**開始**です。  
  
## <a name="see-also"></a>参照  
 [Fabrikam ソリューションの作成と構成](../../adapters-and-accelerators/accelerator-rosettanet/creating-and-configuring-the-fabrikam-solution.md)