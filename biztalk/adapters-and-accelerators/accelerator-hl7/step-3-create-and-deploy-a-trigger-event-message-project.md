---
title: '手順 3: を作成し、トリガー イベント (メッセージ) プロジェクトの配置 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- end-to-end tutorial, trigger events
- trigger events
ms.assetid: 5d21a923-fc2c-4d50-b146-daca0aa26e2a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: deb9d6160fc0b094f0af6f75ab4ab8e5be22462c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998691"
---
# <a name="step-3-create-and-deploy-a-trigger-event-message-project"></a>手順 3: を作成し、トリガー イベント (メッセージ) プロジェクトの配置
この手順では、トリガー イベントのメッセージのスキーマを作成します。 たとえば、入学放電と転送システム (ADT) 病院に情報システム (HIS) にメッセージを送信する場合があります。 このスキーマ、メッセージの形式を定義する必要があります。  
  
### <a name="to-create-the-project-for-the-trigger-event-message"></a>トリガー イベントのメッセージのプロジェクトを作成するには  
  
1. [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]の**ファイル**メニューで、**新規**、] をクリックし、**プロジェクト**します。  
  
2. 新しいプロジェクト ダイアログ ボックスで、**プロジェクトの種類**セクションで、展開**BizTalk プロジェクト**、 をクリックし、 **BTAHL7Projects**します。  
  
3. テンプレート の  **BTAHL7 の空のプロジェクト**で、**名前**ボックスに「 **BTAHL7V231Body プロジェクト**順にクリックします**ok**します。  
  
4. ソリューション エクスプ ローラーで、新しいプロジェクトのノードで右クリック**参照**、 をクリックし、**参照の追加**します。  
  
5. 参照の追加 ダイアログ ボックスで、上、**プロジェクト** タブで  **BTAHL7V231Common Project1**、 をクリックして**追加**、順にクリックします**ok**。  
  
## <a name="step-3a-add-the-schema"></a>手順 3 a: スキーマの追加  
 新しいスキーマをプロジェクトに追加するのにには、次の手順を使用します。  
  
#### <a name="to-add-the-schema-to-the-project"></a>スキーマをプロジェクトに追加するには  
  
1.  ソリューション エクスプ ローラーで右クリック**BTAHL7V231Body プロジェクト**、 をポイント**追加**、 をクリックし、**新しい項目の**します。  
  
2.  追加新しい項目] ダイアログ ボックスで、**カテゴリ**セクションで、展開**BizTalk プロジェクトの項目**、し、[ **BTAHL7 スキーマ**します。  
  
3.  ダブルクリックして、[テンプレート] セクションで**BTAHL7 スキーマ**します。  
  
4.  HL7 スキーマの選択 ダイアログ ボックスで、次の手順を実行します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**Message クラス**|既定のままに**V2.X**選択します。|  
    |**[バージョン]**|選択**2.3.1**します。|  
    |**メッセージの種類**|選択**ADT**します。|  
    |**トリガー イベント**|選択**A03**します。|  
  
5.  をクリックして**完了**スキーマをプロジェクトに追加します。  
  
## <a name="step-3b-assign-a-strong-key-to-the-assembly-and-deploy"></a>手順 3 b: アセンブリに厳密なキーを割り当てるとデプロイ  
 アセンブリに厳密なキーを割り当てるし、アセンブリを配置するには、次の手順を使用します。  
  
#### <a name="to-assign-a-strong-key-and-deploy-the-assembly"></a>強力なキーを割り当てるし、アセンブリを展開するには  
  
1. ソリューション エクスプ ローラーで右クリックして**BTAHL7V231Body プロジェクト**、 をクリックし、**プロパティ**します。  
  
2. プロジェクト プロパティ ページ ページで、次のようにクリックします。**アセンブリ**します。  
  
3. 右側のペインでスクロールして、**厳密な名前**セクションで、フィールドの右側をクリックして**アセンブリ キー ファイル**、クリックして、省略記号 (**.**) ボタンをクリックします。  
  
4. アセンブリ キー ファイル ダイアログ ボックスを参照\<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\End ツー エンド チュートリアルについては、アクセラレータ クリックして**key.snk**、 をクリックし、**オープン**します。  
  
5. プロジェクト プロパティ ページ] ダイアログ ボックスで、[ **OK**変更を保存します。  
  
6. ソリューション エクスプ ローラーで右クリックして**BTAHL7V231Body プロジェクト**、 をクリックし、**デプロイ**します。 成功メッセージが出力ウィンドウに表示を確認します。  
  
   > [!NOTE]
   >  デプロイが成功したメッセージが表示されない場合は、使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]スキーマのトラブルシューティングを行う。  
  
   進みます[手順 4: 作成、ADT を受け入れるための受信ポート ^ A03 メッセージ MLLP アダプターを使用して ADT システムから](../../adapters-and-accelerators/accelerator-hl7/step-4-create-receive-port-to-accept-adt^a03-messages-from-adt-using-mllp.md)します。