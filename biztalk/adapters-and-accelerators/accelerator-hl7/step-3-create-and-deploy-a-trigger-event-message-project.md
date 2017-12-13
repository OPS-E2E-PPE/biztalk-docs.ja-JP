---
title: "手順 3: を作成し、トリガー イベント (メッセージ) プロジェクトを配置 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- end-to-end tutorial, trigger events
- trigger events
ms.assetid: 5d21a923-fc2c-4d50-b146-daca0aa26e2a
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 49fd078f64cbd4163eef648f7a0d58fe6e8db6b2
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="step-3-create-and-deploy-a-trigger-event-message-project"></a>手順 3: を作成し、トリガー イベント (メッセージ) プロジェクトの配置
この手順では、トリガーのイベント メッセージのスキーマを作成します。 たとえば、受付放電して転送システム (ADT) 病院情報システム (HIS) にメッセージを送信する場合があります。 このスキーマに、メッセージの書式を定義する必要があります。  
  
### <a name="to-create-the-project-for-the-trigger-event-message"></a>トリガー イベント メッセージのプロジェクトを作成するには  
  
1.  [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]の**ファイル** メニューのをポイント**新規**をクリックし、**プロジェクト**です。  
  
2.  新しいプロジェクト ダイアログ ボックスで、**プロジェクトの種類**セクションで、展開**BizTalk プロジェクト**、順にクリック**BTAHL7Projects**です。  
  
3.  テンプレート の  **BTAHL7 の空のプロジェクト**で、**名前**ボックスに、入力**BTAHL7V231Body プロジェクト**、順にクリック**ok**です。  
  
4.  ソリューション エクスプ ローラーで、新しいプロジェクトのノードの下を右クリックして**参照**、クリックして**参照の追加**です。  
  
5.  参照の追加 ダイアログ ボックスで、**プロジェクト** タブで、 **BTAHL7V231Common Project1**、 をクリックして**追加**、順にクリック**ok**です。  
  
## <a name="step-3a-add-the-schema"></a>手順 3: スキーマの追加  
 次の手順を使用して、新しいスキーマをプロジェクトに追加します。  
  
#### <a name="to-add-the-schema-to-the-project"></a>スキーマをプロジェクトに追加するには  
  
1.  ソリューション エクスプ ローラーで右クリック**BTAHL7V231Body プロジェクト**、 をポイント**追加**、クリックして**新しい項目の**します。  
  
2.  追加で新しい項目 ダイアログ ボックス、、**カテゴリ**セクションで、展開**BizTalk プロジェクトの項目**、し、 **BTAHL7 スキーマ**です。  
  
3.  [テンプレート] セクションをダブルクリックして**BTAHL7 スキーマ**です。  
  
4.  HL7 スキーマの選択 ダイアログ ボックスで、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**Message クラス**|既定のままにして**V2.X**選択します。|  
    |**バージョン**|選択**2.3.1**です。|  
    |**メッセージの種類**|選択**ADT**です。|  
    |**トリガー イベント**|選択**A03**です。|  
  
5.  をクリックして**完了**スキーマをプロジェクトに追加します。  
  
## <a name="step-3b-assign-a-strong-key-to-the-assembly-and-deploy"></a>手順 3 b: アセンブリに厳密なキーを割り当てると展開  
 アセンブリに厳密なキーを割り当てるし、アセンブリを配置するには、次の手順を使用します。  
  
#### <a name="to-assign-a-strong-key-and-deploy-the-assembly"></a>強力なキーを割り当てるし、アセンブリを展開するには  
  
1.  ソリューション エクスプ ローラーで右クリック**BTAHL7V231Body プロジェクト**、クリックして**プロパティ**です。  
  
2.  プロジェクト プロパティ ページ ページで、をクリックして**アセンブリ**です。  
  
3.  右側のペインでスクロールして、**厳密な名前**セクションで、フィールドの右側をクリックして**アセンブリ キー ファイル**、クリックして、省略記号 (**.**) ボタンをクリックします。  
  
4.  アセンブリ キー ファイル ダイアログ ボックスでを参照\<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\End エンドツー エンド チュートリアルでは、アクセラレータ クリックして**key.snk**、クリックして**開く**です。  
  
5.  プロジェクト プロパティ ページ] ダイアログ ボックスで、[ **OK**して変更を保存します。  
  
6.  ソリューション エクスプ ローラーで右クリック**BTAHL7V231Body プロジェクト**、クリックして**展開**です。 成功メッセージが出力ウィンドウに表示を確認します。  
  
    > [!NOTE]
    >  展開の成功メッセージが表示されない場合を使用して[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]スキーマをトラブルシューティングします。  
  
 進みます[手順 4: 作成、ADT を受け入れるための受信ポート ^ MLLP アダプターを使用して ADT システムから A03 メッセージ](../../adapters-and-accelerators/accelerator-hl7/step-4-create-receive-port-to-accept-adt^a03-messages-from-adt-using-mllp.md)です。