---
title: 手順 4:スキーマの作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message enrichment tutorial, schemas
- creating, schemas
- schemas, creating
ms.assetid: 81b1f538-9743-433a-87f9-a423dcb868c8
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 58f3e45216c9a38faf13001eb3842ef0db4976d9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65288018"
---
# <a name="step-4-create-the-schemas"></a>手順 4:スキーマを作成します。
この手順で新しいプロジェクトを作成する (**BTAHL7 プロジェクト**) このプロジェクトの成果物を格納している: スキーマ、マップ、およびオーケストレーションします。 スキーマを作成し (**Doorbell.xsd**) XML でエンコードされた受信メッセージ、および既存のスキーマを選択します (**ADT_A04_22_GLO_DEF.xsd**) 送信 HL7 でエンコードされたメッセージ。 これらのスキーマを使用すると、オーケストレーション内で交換するメッセージの構造を定義します。  

### <a name="to-create-the-schemas"></a>スキーマを作成するには  

1. **[ファイル]** メニューの **[新規作成]** をポイントし、 **[プロジェクト]** をクリックします。  

2. 新しいプロジェクト ダイアログ ボックスで、展開、 **BizTalk プロジェクト**フォルダー、およびクリック、 **BTAHL7Projects**フォルダー。  

3. **テンプレート**ウィンドウで、をクリックして**BTAHL7 の空のプロジェクト**します。  

4. **名前**フィールドに「 **BTAHL7 プロジェクト**プロジェクト名として。  

5. **ソリューション**フィールドで、**ソリューションに追加**します。  

6. **場所**フィールドしていることを確認するには、  **\<*ドライブ*\>: \Tutorial\BTAHL7V22Common**パスです。  

7. をクリックして**OK**を新しいプロジェクトを開きます。  

   > [!NOTE]
   >  [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] ソリューション エクスプ ローラーに新しいプロジェクトを追加します。 プロジェクト フォルダーを追加および内のファイルを作成します、 \<*ドライブ*\>: \Tutorial\\**BTAHL7V22Common**プロジェクト フォルダーです。  

8. ソリューション エクスプ ローラーで右クリックし、 **BTAHL7 プロジェクト**プロジェクトをポイントして、**追加**、 をクリックし、**新しい項目の**。  

9. 新しい項目の追加 - BTAHL7 プロジェクト] ダイアログ ボックスで、**カテゴリ**ウィンドウで、をクリックして**スキーマ ファイル**、し、[、**テンプレート**ウィンドウで、をクリックして**スキーマ**.  

10. **名前**フィールドに「 **Doorbell.xsd**にスキーマの名前。  

11. クリックして**追加**に空のスキーマを BizTalk エディターで開きます。  

12. **\<スキーマ\>** ツリーで、右クリックし、**ルート**ノード、およびクリック**の名前を変更**します。  

13. 型**DoorbellRoot**として、新しい名前とキーを押します**Enter**します。  

14. 右クリックし、 **DoorbellRoot**に**スキーマ ノードの挿入**、 をクリックし、**子フィールド要素**(フィールドごとにこの手順を繰り返して、次のフィールドを追加するには要素の場合):  

    -   **FirstName**  

    -   **MiddleName**  

    -   **LastName**  

    -   **SSN**  

15. ソリューション エクスプ ローラーで右クリック**BTAHL7 プロジェクト**、 をポイント**追加**、 をクリックし、**新しい項目の**します。  

16. 新しい項目の追加 - BTAHL7 プロジェクト ダイアログ ボックスで、**カテゴリ**ウィンドウで、をクリックして**BTAHL7 スキーマ**、順にクリックします**追加**します。  

17. HL7 スキーマの選択 ダイアログ ボックスで、**メッセージ クラス**ボックスで、 **V2.X**、し、**スキーマの詳細**ウィンドウで、次の操作を行います。  


    |     プロパティ      |                                     目的                                     |
    |-------------------|------------------------------------------------------------------------------------|
    |    **バージョン**    |    HL7 メッセージのバージョン番号を選択します。 このチュートリアルでは使用**2.2**します。    |
    | **メッセージの種類**  |           HL7 メッセージの種類を選択します。 このチュートリアルでは使用**ADT**します。           |
    | **トリガー イベント** | HL7 メッセージのトリガー イベントの値を選択します。 このチュートリアルでは使用**A04**します。 |


18. クリックして**完了**ADT_A04_22_GLO_DEF.xsd (患者の登録) スキーマをプロジェクトに追加します。 HL7 スキーマの選択 ダイアログ ボックスを閉じます。  

19. ソリューション エクスプ ローラーで  **BTAHL7 プロジェクト**、右クリックして**参照**順にクリックします**参照の追加**します。  

20. 参照の追加 ダイアログ ボックスでの**プロジェクト** タブで、、 **BTAHL7V22Common**プロジェクトで、をクリックして**追加**、順にクリックします**OK**。  

    > [!NOTE]
    >  元のプロジェクトへの参照を追加できるように[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]HL7 スキーマを正しく認識します。  

21. ソリューション エクスプ ローラーで  **BTAHL7 プロジェクト**、右クリックして**参照**順にクリックします**参照の追加**します。  

22. [参照の追加] ダイアログ ボックスで、**参照**タブ。**検索対象の**ボックスで、移動\<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\End ツー エンドのチュートリアルのアクセラレータ\Tutorial_BTAHL7Drop\Bin します。 クリックして**Microsoft.Solutions.BTAHL7.HL7Schemas.dll**、 をクリックして**追加**、順にクリックします**OK**します。  

    続行する[手順 5。スキーマ プロパティを昇格させる](../../adapters-and-accelerators/accelerator-hl7/step-5-promote-schema-properties.md)します。  

## <a name="see-also"></a>参照  
 [メッセージ強化のチュートリアル](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)