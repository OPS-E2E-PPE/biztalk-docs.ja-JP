---
title: '手順 3: 作成し、デプロイをトリガー イベント (メッセージ) _hl7_main |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- interrogative tutorial, trigger events
ms.assetid: 90b65ad1-7953-4009-a1eb-1c2a85c7980a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 263d131fffbeec996904d303be3fecd1eacf40c8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013171"
---
# <a name="step-3-create-and-deploy-a-trigger-event-message-projecthl7main"></a>手順 3: 作成し、デプロイをトリガー イベント (メッセージ) _hl7_main
この手順では、トリガー イベントのメッセージで使用されるスキーマを作成します。 たとえば、入学放電と転送システム (ADT) をメッセージを送信病院情報システム (HIS) にします。 このスキーマを使用するには、メッセージの形式を定義します。  
  
### <a name="to-create-the-project-for-the-trigger-event-message"></a>トリガー イベントのメッセージのプロジェクトを作成するには  
  
1. [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], の **ファイル** メニューをポイント **新規**, 、クリックして **プロジェクト**します。  
  
2. 新しいプロジェクト ダイアログ ボックスで、**プロジェクトの種類**一覧で、展開**BizTalk プロジェクト**、 をクリックし、 **BTAHL7Projects**します。  
  
3. **テンプレート**一覧で、 **BTAHL7 の空のプロジェクト**します。  
  
4. **名前**フィールドに「 **BTAHL7V24Body プロジェクト**順にクリックします**OK**します。  
  
5. ソリューション エクスプ ローラーで、新しいノードの下で**BTAHL7V24Body**プロジェクトを右クリックして**参照**、順にクリックします**参照の追加**します。  
  
6. 参照の追加 ダイアログ ボックスで、、**プロジェクト** タブで  **Interrogative_24Schemas**、 をクリックして**追加**、順にクリックします**OK**します。  
  
## <a name="step-3a-add-the-schemas"></a>手順 3 a: スキーマを追加します  
 次の手順を使用して、新しいスキーマをプロジェクトに追加します。  
  
#### <a name="to-add-the-schemas-to-the-project"></a>スキーマをプロジェクトに追加するには  
  
1.  ソリューション エクスプ ローラーで右クリック**BTAHL7V24Body プロジェクト**、 をポイント**追加**、 をクリックし、**新しい項目の**します。  
  
2.  新しい項目の追加 ダイアログ ボックスで、 **BizTalk プロジェクトの項目**、し、ダブルクリック**BTAHL7 スキーマ**右側のペインでします。  
  
3.  HL7 スキーマの選択 ダイアログ ボックスで、次の手順を実行します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**Message クラス**|保持**V2.X**選択します。|  
    |**[バージョン]**|選択**2.4**します。|  
    |**メッセージの種類**|選択**QRY**します。|  
    |**トリガー イベント**|選択**Q01**します。|  
  
4.  をクリックして**完了**スキーマをプロジェクトに追加します。  
  
     これには、クエリのスキーマ ファイル QRY_Q01_24_GLO_DEF.xsd が作成されます。  
  
    > [!NOTE]
    >  HL7 スキーマの選択 ダイアログ ボックスを終了しないでください。  
  
5.  HL7 スキーマの選択 ダイアログ ボックスで、次の手順を実行します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**Message クラス**|保持**V2.X**選択します。|  
    |**[バージョン]**|選択**2.4**します。|  
    |**メッセージの種類**|選択**DSR**します。|  
    |**トリガー イベント**|選択**Q01**します。|  
  
6.  をクリックして**完了**スキーマをプロジェクトに追加します。  
  
     これには、応答スキーマ ファイル DSR_Q01_24_GLO_DEF.xsd が作成されます。  
  
7.  クリックして**キャンセル**を閉じる、 **HL7 スキーマの選択** ダイアログ ボックス。  
  
## <a name="step-3b-assign-a-strong-key-to-the-assembly-and-deploy"></a>手順 3 b: アセンブリに厳密なキーを割り当てるとデプロイ  
 アセンブリに厳密なキーを割り当てるし、アセンブリを配置するには、次の手順を使用します。  
  
#### <a name="to-assign-a-strong-key-and-deploy-the-assembly"></a>強力なキーを割り当てるし、アセンブリを展開するには  
  
1. ソリューション エクスプ ローラーで右クリックして**BTAHL7V24Body**プロジェクトをクリックして**プロパティ**します。  
  
2. **BTAHL7V24Body プロパティ ページ**ダイアログ ボックスで、をクリックして**アセンブリ**します。  
  
3. 右側のペインでスクロールして、**厳密な名前**セクションで、フィールドの右側をクリックして**アセンブリ キー ファイル**、省略記号 (...) ボタンを順にクリックします。  
  
4. **アセンブリ キー ファイル** ダイアログ ボックスを参照\<*ドライブ*\>: \Program Files\\Microsoft BizTalk\<バージョン\>HL7\SDK\Interrogative チュートリアルでは、アクセラレータのをクリックして**key.snk**、 をクリックし、**オープン**します。  
  
5. **BTAHL7V24Body プロパティ ページ**ダイアログ ボックスで、をクリックして**OK**変更を保存します。  
  
6. ソリューション エクスプ ローラーで右クリックして**BTAHL7V24Body プロジェクト**、 をクリックし、**デプロイ**します。 成功メッセージが出力ウィンドウに表示を確認します。  
  
   > [!NOTE]
   >  デプロイが成功したメッセージが表示されない場合は、使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]スキーマのトラブルシューティングを行う。  
  
   進みます[手順 4: 作成、受信ポート ADT クエリ メッセージの受け入れの](../../adapters-and-accelerators/accelerator-hl7/step-4-create-the-receive-port-for-accepting-adt-query-messages.md)します。