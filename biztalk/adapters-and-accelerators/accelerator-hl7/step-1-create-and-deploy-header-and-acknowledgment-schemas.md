---
title: 手順 1:ヘッダーと確認スキーマ作成および展開 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- end-to-end tutorial, header schemas
- header schemas
ms.assetid: 3ff013a4-6c67-4bac-be97-81b2dc5b6119
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 03782a8c2692dea4af7df9e3e03526a919940257
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65288897"
---
# <a name="step-1-create-and-deploy-header-and-acknowledgment-schemas"></a>手順 1:ヘッダーと確認スキーマ作成およびデプロイ
メッセージ インスタンスのヘッダー (MSH セグメント) を検証するのにには、ヘッダー スキーマを使用します。 受信確認メッセージのインスタンスを生成するのにには、受信確認スキーマを使用します。 このプロセスは、すべてのスキーマ バージョンの間で共通[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2.X。  
  
### <a name="to-create-the-header-and-acknowledgment-schemas"></a>ヘッダーと受信確認スキーマを作成するには  
  
1. 開始**Microsoft Visual Studio 2012**します。  
  
2. [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], の **ファイル** メニューをポイント **新規**, 、クリックして **プロジェクト**します。  
  
3. 新しいプロジェクト] ダイアログ ボックスで、**プロジェクトの種類**セクションで、展開**BizTalk プロジェクト**、し、[ **BTAHL7Projects**します。  
  
4. テンプレート セクションで**BTAHL7V2XCommon プロジェクト**、 をクリックし、 **OK**。  
  
    ソリューション エクスプ ローラーでは、(ACK_24_GLO_DEF.xsd ACK_25_GLO_DEF.xsd、および MSH_25_GLO_DEF.xsd) の 3 つのスキーマをプロジェクトに含まれることに注意してください。  
  
## <a name="step-1a-assign-a-strong-key-to-the-assembly-and-deploy"></a>手順 1 a:アセンブリに厳密なキーを割り当てるとデプロイ  
 アセンブリに厳密なキーを割り当てるし、アセンブリを配置するには、次の手順を使用します。  
  
#### <a name="to-assign-a-strong-key-and-deploy-the-assembly"></a>強力なキーを割り当てるし、アセンブリを展開するには  
  
1. 開始**Visual Studio 2012 のコマンド プロンプト**します。  
  
2. [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]コマンド プロンプトで、参照、 \<*ドライブ*\>: \Program Files\\Microsoft BizTalk\<バージョン\>Accelerator for HL7 \SDK\End-to-Endチュートリアル フォルダーです。  
  
3. コマンド プロンプトで「 **sn – k key.snk**し、ENTER キーを押します。 出力 ウィンドウで次の成功メッセージが表示されることを確認し、コマンド ウィンドウを閉じます。  
  
    **「キーの key.snk に書き込まれるペアです。」**  
  
   > [!NOTE]
   >  適切なメッセージが表示されない場合は、使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]アセンブリのトラブルシューティングを行う。  
  
4. ソリューション エクスプ ローラーで右クリックして**BTAHL7V2XCommon Project1**、 をクリックし、**プロパティ**します。  
  
5. BTAHL7V2XCommon Project1 プロパティ ページ ページで、次のようにクリックします。**アセンブリ**します。  
  
6. 右側のペインでスクロールして、**厳密な名前**セクションで、フィールドの右側をクリックして**アセンブリ キー ファイル**、クリックして、省略記号 (**.**) ボタンをクリックします。  
  
7. アセンブリ キー ファイル ダイアログ ボックスを参照\<*ドライブ*\>: \Program Files\\Microsoft BizTalk\<バージョン\>HL7\SDK\End ツー エンド チュートリアルについては、アクセラレータ選択**key.snk**、 をクリックし、**オープン**します。  
  
8. BTAHL7V2XCommon プロジェクトのプロパティ ページで、次のようにクリックします。 **OK** 、変更を保存します。  
  
9. [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]の**ソリューション エクスプ ローラー**、右クリック**BTAHL7V2XCommon プロジェクト**、順にクリックします**デプロイ**します。 成功メッセージが出力ウィンドウに表示を確認します。  
  
   > [!NOTE]
   >  デプロイの適切なメッセージが表示されない場合は、使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]デプロイのトラブルシューティングを行う。  
  
   続行する[手順 2。V2.3.1 の一般的なスキーマを作成する](../../adapters-and-accelerators/accelerator-hl7/step-2-create-common-schemas-for-v2-3-1.md)します。