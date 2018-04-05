---
title: '手順 1: を作成し、共通のヘッダーと受信確認スキーマを展開 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- interrogative tutorial, headers
ms.assetid: e0f11f58-9a8c-4567-a537-3d182fa7dce2
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 222f78232afd988e5bb47b2aa12bb75eb4635ce5
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="step-1-create-and-deploy-common-header-and-acknowledgment-schemas"></a>手順 1: を作成し、共通のヘッダーと受信確認スキーマを展開
メッセージ インスタンスのヘッダー (MSH セグメント) を検証するのにには、ヘッダー スキーマを使用します。 メッセージ インスタンスの確認を生成するのにには、受信確認スキーマを使用します。 このプロセスは、HL7 スキーマのすべてのバージョンで共通です。  
  
### <a name="to-create-the-header-and-acknowledgment-schemas"></a>ヘッダーおよび受信確認応答スキーマを作成するには  
  
1.  開始**Microsoft Visual Studio 2012**です。  
  
2.  [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]の**ファイル** メニューのをポイント**新規**、クリックして**プロジェクト**です。  
  
3.  新しいプロジェクト] ダイアログ ボックスで、**プロジェクトの種類**一覧で、展開**BizTalk プロジェクト**、し、[ **BTAHL7Projects**です。  
  
4.  **テンプレート**一覧で、 **BTAHL7V2XCommon プロジェクト**です。  
  
5.  **名前**フィールドに「 **Interrogative_2XSchemas**、順にクリック**OK**です。  
  
     ソリューション エクスプ ローラーで、プロジェクトに 3 つのスキーマ (ACK_24_GLO_DEF.xsd、ACK_25_GLO_DEF.xsd、および MSH_25_GLO_DEF.xsd) が含まれていることを確認します。  
  
     Visual Studio は開いたままにしておきます。  
  
## <a name="step-1a-assign-a-strong-key-to-the-assembly-and-deploy"></a>手順 1 a: アセンブリに厳密なキーを割り当てると展開  
 アセンブリに厳密なキーを割り当てるし、アセンブリを配置するには、次の手順を使用します。  
  
#### <a name="to-assign-a-strong-key-and-deploy-the-assembly"></a>強力なキーを割り当てるし、アセンブリを展開するには  
  
1.  開始**Visual Studio 2012 コマンド プロンプト**です。  
  
2.  [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]コマンド プロンプトで、ディレクトリに移動、 \<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\Interrogative のアクセラレータTutorial フォルダーです。  
  
3.  コマンド プロンプトで次のように入力します。 **sn – k key.snk**、キーを押します**Enter**です。 成功メッセージが出力ウィンドウに表示されることを確認します。  
  
    > [!NOTE]
    >  使用して、適切なメッセージが表示されない場合[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]アセンブリをトラブルシューティングします。  
  
4.  ソリューション エクスプ ローラーで右クリック**Interrogative_2XSchemas**プロジェクトをクリックして**プロパティ**です。  
  
5.  Interrogative_2XSchemas プロパティ ページ] ダイアログ ボックスで、[**アセンブリ**です。  
  
6.  右側のペインでスクロールして、**厳密な名前**セクションで、フィールドの右側をクリックして**アセンブリ キー ファイル**、省略記号 (...) ボタンをクリックします。  
  
7.  アセンブリ キー ファイル ダイアログ ボックスでを参照\<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\Interrogative チュートリアルでは、アクセラレータをクリックして**key.snk**、クリックして**開く**です。  
  
8.  Interrogative_2XSchemas プロパティ ページ] ダイアログ ボックスで、[ **OK**して変更を保存します。  
  
9. [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、ソリューション エクスプ ローラーで右クリック**Interrogative_2XSchemas**プロジェクトをクリックして**展開**です。 成功メッセージが出力ウィンドウに表示を確認します。  
  
    > [!NOTE]
    >  使用して、正しい配置メッセージが表示されない場合[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]展開のトラブルシューティングにします。  
  
 進みます[手順 2: V2.4 の一般的なスキーマを作成する](../../adapters-and-accelerators/accelerator-hl7/step-2-create-common-schemas-for-v2-4.md)です。