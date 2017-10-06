---
title: "手順 1: を作成し、ヘッダーと受信確認スキーマを展開 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- end-to-end tutorial, header schemas
- header schemas
ms.assetid: 3ff013a4-6c67-4bac-be97-81b2dc5b6119
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0bfab230d919c2cb7f8c05d58b87cdeea6033423
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-create-and-deploy-header-and-acknowledgment-schemas"></a>手順 1: を作成し、ヘッダーと受信確認スキーマを展開
メッセージ インスタンスのヘッダー (MSH セグメント) を検証するのにには、ヘッダー スキーマを使用します。 メッセージ インスタンスの確認を生成するのにには、受信確認スキーマを使用します。 このプロセスは、すべてのスキーマ バージョンの間で共通[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2.X です。  
  
### <a name="to-create-the-header-and-acknowledgment-schemas"></a>ヘッダーおよび受信確認応答スキーマを作成するには  
  
1.  開始**Microsoft Visual Studio 2012**です。  
  
2.  [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]の**ファイル**メニューのをポイント**新規**、クリックして**プロジェクト**です。  
  
3.  新しいプロジェクト] ダイアログ ボックスで、**プロジェクトの種類**セクションで、展開**BizTalk プロジェクト**、し、[ **BTAHL7Projects**です。  
  
4.  テンプレート セクションで、 **BTAHL7V2XCommon プロジェクト**、順にクリック**ok**です。  
  
     ソリューション エクスプローラで、プロジェクトに 3 つのスキーマ (ACK_24_GLO_DEF.xsd ACK_25_GLO_DEF.xsd および MSH_25_GLO_DEF.xsd) が含まれていることを確認します。  
  
## <a name="step-1a-assign-a-strong-key-to-the-assembly-and-deploy"></a>手順 1 a: アセンブリに厳密なキーを割り当てると展開  
 アセンブリに厳密なキーを割り当てるし、アセンブリを配置するには、次の手順を使用します。  
  
#### <a name="to-assign-a-strong-key-and-deploy-the-assembly"></a>強力なキーを割り当てるし、アセンブリを展開するには  
  
1.  開始**Visual Studio 2012 コマンド プロンプト**です。  
  
2.  [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]コマンド プロンプトで、参照、 \<*ドライブ*>: \Program Files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk\<バージョン > Accelerator for HL7 \SDK\End-to-End Tutorial フォルダーです。  
  
3.  コマンド プロンプトで次のように入力します。 **sn – k key.snk**、ENTER キーを押します。 [出力] ウィンドウで次の成功メッセージを表示することを確認し、コマンド ウィンドウを閉じます。  
  
     **「キーペア key.snk に書き込まれます。」**  
  
    > [!NOTE]
    >  使用して、適切なメッセージが表示されない場合[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]アセンブリをトラブルシューティングします。  
  
4.  ソリューション エクスプ ローラーで右クリック**BTAHL7V2XCommon Project1**、クリックして**プロパティ**です。  
  
5.  BTAHL7V2XCommon Project1 プロパティ ページ ページで、をクリックして**アセンブリ**です。  
  
6.  右側のペインでスクロールして、**厳密な名前**セクションで、フィールドの右側をクリックして**アセンブリ キー ファイル**、クリックして、省略記号 (**.**) ボタンをクリックします。  
  
7.  アセンブリ キー ファイル ダイアログ ボックスでを参照\<*ドライブ*>: \Program Files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk\<バージョン > Accelerator for HL7\SDK\End エンドツー エンド チュートリアルでは、選択**key.snk**、クリックして**開く**です。  
  
8.  BTAHL7V2XCommon プロジェクトのプロパティ ページで、 **OK**して変更を保存します。  
  
9. [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]で、**ソリューション エクスプ ローラー**を右クリックして**BTAHL7V2XCommon プロジェクト**、クリックして**展開**です。 成功メッセージが出力ウィンドウに表示を確認します。  
  
    > [!NOTE]
    >  使用して、正しい配置メッセージが表示されない場合[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]展開のトラブルシューティングにします。  
  
 進みます[手順 2: V2.3.1 の一般的なスキーマを作成する](../../adapters-and-accelerators/accelerator-hl7/step-2-create-common-schemas-for-v2-3-1.md)です。