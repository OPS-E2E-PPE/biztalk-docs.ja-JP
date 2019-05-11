---
title: 手順 7:DoubleAction SDK サンプルのビルドと |Microsoft Docs
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
ms.openlocfilehash: 6ef2bee03470c6cf3792310467802e05628dd4b4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65280674"
---
# <a name="step-7-building-and-deploying-the-doubleaction-sdk-sample"></a>手順 7:DoubleAction SDK サンプルのビルドと
DoubleAction.odx サンプルは、ダブル アクションの Partner Interface Process (Pip) の応答を自動的に生成するオーケストレーションを実装する方法を示しています。 0c2、0 C 4、3 a 2、3A4 とします。 追加のダブル アクション Pip をサポートするには、このサンプル プロジェクトを拡張することができます。  
  
 Fabrikam が 4 つの Pip のいずれかを使用して、要求されるたびに、Fabrikam に自動的に応答を送信するのにには、このサンプルを使用します。  
  
### <a name="to-build-and-initialize-the-doubleaction-sample"></a>ビルドして初期化 DoubleAction サンプル  
  
1. コマンド プロンプト ウィンドウで、Contoso のコンピューターには、次のフォルダーに移動します。   
   *\<ドライブ\>*: \Program Files\\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\pipautomation\doubleaction\\します。  
  
   > [!NOTE]
   >  セットアップ プログラムを実行する前に、メモ帳で DoubleAction.sql ファイル (上記のフォルダー) でを開きます。 **ファイル** メニューのをクリックして**付けて**します。 **エンコード**ボックスで、 **ANSI**クリックしてドロップダウン リストから**保存**します。 をクリックして**はい**既存のファイルを上書きします。  
  
2. BizTalk Server のインストールが SQL Server 2008 R2 または 2008 SP1 を実行している場合は、同じフォルダーに setupx64.bat を実行します。 バッチ ファイルでは、次の操作が実行されます。  
  
   - SQL ストアド プロシージャを作成します (`PipAutomationGetAction`)、アクション メッセージを MessagesToLOB テーブルから取得する、BTARNDATA データベースです。  
  
   - HeaderHelper .NET プロジェクトをコンパイルし、グローバル アセンブリ キャッシュにアセンブリを登録します。  
  
   - 作成し、バインド、 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] SQL 受信ポート (MessagesToLOB_Receive_Port)。  
  
   - 受信場所 (MessagesToLOB_Receive_Location) を有効にします。  
  
   - コンパイルし、ダブル アクション PIPAutomation オーケストレーション (DoubleAction.odx) を展開します。  
  
   - [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] オーケストレーションをバインドして、開始します。  
  
     > [!NOTE]
     >  サンプルでは、コンパイル中にいくつかの警告が表示されます。 これらの警告を無視することができます。  
  
     > [!NOTE]
     >  DoubleAction.odx にバインドされていることを確認**MessagesToLOB_Receive_Port**オーケストレーションが開始されているとします。  
  
3. BizTalk Server 管理コンソールで、展開、 **BizTalk グループ**、**アプリケーション**、および**BizTalk アプリケーション 1**ノード。 をクリックして、**オーケストレーション**ノード。 右クリックし、 **DoubleAction**オーケストレーション、およびクリック**プロパティ**します。 [プロパティ] ダイアログ ボックスで、**バインド**ノード、および設定して、**ホスト**に **[biztalkserverapplication]** 設定と、**受信ポート**に **[messagetolob_receiveport]** します。 **[OK]** をクリックします。 右クリックし、 **DoubleAction**オーケストレーション、およびクリック**開始**します。  
  
## <a name="see-also"></a>参照  
 [Fabrikam ソリューションの作成と構成](../../adapters-and-accelerators/accelerator-rosettanet/creating-and-configuring-the-fabrikam-solution.md)