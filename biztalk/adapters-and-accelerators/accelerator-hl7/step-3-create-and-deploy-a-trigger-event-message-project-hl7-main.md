---
title: "手順 3: を作成し、トリガー イベント (メッセージ) Project_hl7_main の展開 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: interrogative tutorial, trigger events
ms.assetid: 90b65ad1-7953-4009-a1eb-1c2a85c7980a
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ff7abfcf363d26d068fab067378eb61d5bcf5c3c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-3-create-and-deploy-a-trigger-event-message-projecthl7main"></a>手順 3: を作成し、トリガー イベント (メッセージ) Project_hl7_main の展開
この手順では、トリガー イベント メッセージで使用されるスキーマを作成します。 たとえば、受付放電して転送システム (ADT) をメッセージを送信病院情報システム (HIS) にします。 このスキーマを使用するには、メッセージの形式を定義します。  
  
### <a name="to-create-the-project-for-the-trigger-event-message"></a>トリガー イベント メッセージのプロジェクトを作成するには  
  
1.  [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]の**ファイル**メニューのをポイント**新規**、クリックして**プロジェクト**です。  
  
2.  新しいプロジェクト ダイアログ ボックスで、**プロジェクトの種類**一覧で、展開**BizTalk プロジェクト**、順にクリック**BTAHL7Projects**です。  
  
3.  **テンプレート**一覧で、クリックして**BTAHL7 の空のプロジェクト**です。  
  
4.  **名前**フィールドに「 **BTAHL7V24Body プロジェクト**順にクリック**OK**です。  
  
5.  ソリューション エクスプ ローラーの新しいノードの下**BTAHL7V24Body**プロジェクトを右クリックして**参照**、クリックして**参照の追加**です。  
  
6.  [参照の追加] ダイアログ ボックス、**プロジェクト**] タブで [ **Interrogative_24Schemas**、をクリックして**追加**、順にクリック**[ok]**です。  
  
## <a name="step-3a-add-the-schemas"></a>手順 3: のスキーマを追加  
 次の手順を使用して、新しいスキーマをプロジェクトに追加します。  
  
#### <a name="to-add-the-schemas-to-the-project"></a>プロジェクトにスキーマを追加するには  
  
1.  ソリューション エクスプ ローラーで右クリック**BTAHL7V24Body プロジェクト**、をポイント**追加**、クリックして**新しい項目の**します。  
  
2.  [新しい項目の追加] ダイアログ ボックスで、展開**BizTalk プロジェクトの項目**、順にダブルクリック**BTAHL7 スキーマ**右側のウィンドウでします。  
  
3.  HL7 スキーマの選択 ダイアログ ボックスで、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**Message クラス**|保持**V2.X**選択します。|  
    |**バージョン**|選択**2.4**です。|  
    |**メッセージの種類**|選択**クエリ**です。|  
    |**トリガー イベント**|選択**Q01**です。|  
  
4.  をクリックして**完了**スキーマをプロジェクトに追加します。  
  
     これには、クエリのスキーマ ファイル QRY_Q01_24_GLO_DEF.xsd が作成されます。  
  
    > [!NOTE]
    >  HL7 スキーマの選択 ダイアログ ボックスを終了しないでください。  
  
5.  HL7 スキーマの選択 ダイアログ ボックスで、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**Message クラス**|保持**V2.X**選択します。|  
    |**バージョン**|選択**2.4**です。|  
    |**メッセージの種類**|選択**DSR**です。|  
    |**トリガー イベント**|選択**Q01**です。|  
  
6.  をクリックして**完了**スキーマをプロジェクトに追加します。  
  
     これには、応答スキーマ ファイル DSR_Q01_24_GLO_DEF.xsd が作成されます。  
  
7.  をクリックして**キャンセル**を閉じる、 **HL7 スキーマの選択** ダイアログ ボックス。  
  
## <a name="step-3b-assign-a-strong-key-to-the-assembly-and-deploy"></a>手順 3 b: アセンブリに厳密なキーを割り当てると展開  
 アセンブリに厳密なキーを割り当てるし、アセンブリを配置するには、次の手順を使用します。  
  
#### <a name="to-assign-a-strong-key-and-deploy-the-assembly"></a>強力なキーを割り当てるし、アセンブリを展開するには  
  
1.  ソリューション エクスプ ローラーで右クリック**BTAHL7V24Body**プロジェクトをクリックして**プロパティ**です。  
  
2.  **BTAHL7V24Body プロパティ ページ**ダイアログ ボックスで、をクリックして**アセンブリ**です。  
  
3.  右側のペインでスクロールして、**厳密な名前**セクションで、フィールドの右側をクリックして**アセンブリ キー ファイル**、省略記号 (...) ボタンをクリックします。  
  
4.  **アセンブリ キー ファイル**ダイアログ ボックスを参照\<*ドライブ*>: \Program Files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk\<バージョン > Accelerator for HL7\SDK\Interrogative チュートリアルをクリックして**key.snk**、順にクリック**開く**です。  
  
5.  **BTAHL7V24Body プロパティ ページ**ダイアログ ボックスで、をクリックして**OK**変更を保存します。  
  
6.  ソリューション エクスプ ローラーで右クリック**BTAHL7V24Body プロジェクト**、クリックして**展開**です。 成功メッセージが出力ウィンドウに表示を確認します。  
  
    > [!NOTE]
    >  展開の成功メッセージが表示されない場合を使用して[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]スキーマをトラブルシューティングします。  
  
 進みます[手順 4: 作成、ADT クエリ メッセージを受け入れるための受信ポート](../../adapters-and-accelerators/accelerator-hl7/step-4-create-the-receive-port-for-accepting-adt-query-messages.md)です。