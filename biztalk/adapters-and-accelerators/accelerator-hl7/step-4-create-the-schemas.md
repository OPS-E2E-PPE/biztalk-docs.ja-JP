---
title: "手順 4: スキーマの作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- message enrichment tutorial, schemas
- creating, schemas
- schemas, creating
ms.assetid: 81b1f538-9743-433a-87f9-a423dcb868c8
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cbc70a0a00916f0e2b76f4245f80d488bf026bc8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-4-create-the-schemas"></a>手順 4: スキーマを作成します。
この手順で新しいプロジェクトを作成する (**BTAHL7 プロジェクト**) このプロジェクトの成果物を含む: スキーマ、マップ、およびオーケストレーションです。 スキーマを作成し、(**Doorbell.xsd**) を既存のスキーマを選択して受信の XML でエンコードされたメッセージ (**ADT_A04_22_GLO_DEF.xsd**) HL7 エンコードされたメッセージの送信。 これらのスキーマを使用して、オーケストレーション内で交換されるメッセージの構造を定義します。  
  
### <a name="to-create-the-schemas"></a>スキーマを作成するには  
  
1.  **[ファイル]** メニューの **[新規作成]**をポイントし、 **[プロジェクト]**をクリックします。  
  
2.  新しいプロジェクト ダイアログ ボックスで、展開、 **BizTalk プロジェクト**フォルダーをクリックして、 **BTAHL7Projects**フォルダーです。  
  
3.  **テンプレート** ウィンドウで、をクリックして**BTAHL7 の空のプロジェクト**です。  
  
4.  **名前**フィールドに「 **BTAHL7 プロジェクト**プロジェクト名として。  
  
5.  **ソリューション**フィールドで、**ソリューションに追加**です。  
  
6.  **場所**フィールドであることを確認  **\<*ドライブ*>: \Tutorial\BTAHL7V22Common** はパスです。  
  
7.  をクリックして**OK**新しいプロジェクトを開きます。  
  
    > [!NOTE]
    >  [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]ソリューション エクスプ ローラーに新しいプロジェクトを追加します。 プロジェクト フォルダーを追加して内のファイルを作成、 \<*ドライブ*>: \Tutorial\\**BTAHL7V22Common**プロジェクト フォルダーです。  
  
8.  ソリューション エクスプ ローラーで右クリックし、 **BTAHL7 プロジェクト**プロジェクトをポイントし、**追加**、順にクリック**新しい項目の**します。  
  
9. 新しい項目の追加 - BTAHL7 プロジェクト ダイアログ ボックスで、**カテゴリ** ウィンドウで、をクリックして**スキーマ ファイル**、し、、**テンプレート** ウィンドウで、をクリックして**スキーマ**.  
  
10. **名前**フィールドに「 **Doorbell.xsd**にスキーマの名前。  
  
11. をクリックして**追加**に空のスキーマを BizTalk エディターで開きます。  
  
12. **\<スキーマ >**ツリーで、右クリックし、**ルート**ノードをクリックして**の名前を変更**です。  
  
13. 型**DoorbellRoot**新しい名前は、およびキーを押します**Enter**です。  
  
14. 右クリックし、 **DoorbellRoot**に**スキーマ ノードの挿入**、クリックして**子フィールド要素**(フィールドごとにこの手順を繰り返して、次のフィールドを追加するには要素)。  
  
    -   **FirstName**  
  
    -   **MiddleName**  
  
    -   **[氏名]**  
  
    -   **SSN**  
  
15. ソリューション エクスプ ローラーで右クリック**BTAHL7 プロジェクト**、 をポイント**追加**、クリックして**新しい項目の**します。  
  
16. 新しい項目の追加 - BTAHL7 プロジェクト ダイアログ ボックスで、**カテゴリ** ウィンドウで、をクリックして**BTAHL7 スキーマ**、順にクリック**追加**です。  
  
17. HL7 スキーマの選択 ダイアログ ボックスで、**メッセージ クラス**ボックスで、 **V2.X**、し、、**スキーマの詳細** ウィンドウで、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**バージョン**|HL7 メッセージのバージョン番号を選択します。 このチュートリアルで使用して**2.2**です。|  
    |**メッセージの種類**|HL7 メッセージの種類を選択します。 このチュートリアルで使用して**ADT**です。|  
    |**トリガー イベント**|HL7 メッセージのトリガー イベントの値を選択します。 このチュートリアルで使用して**A04**です。|  
  
18. をクリックして**完了**ADT_A04_22_GLO_DEF.xsd (登録患者) スキーマをプロジェクトに追加します。 HL7 スキーマの選択 ダイアログ ボックスを閉じます。  
  
19. ソリューション エクスプ ローラーで、[ **BTAHL7 プロジェクト**を右クリックして**参照**] をクリックし、**参照の追加**です。  
  
20. 参照の追加 ダイアログ ボックスで、**プロジェクト** タブで、、 **BTAHL7V22Common**プロジェクトで、をクリックして**追加**、順にクリック**ok**です。  
  
    > [!NOTE]
    >  元のプロジェクトへの参照を追加できるように[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]HL7 スキーマを正しく認識します。  
  
21. ソリューション エクスプ ローラーで、[ **BTAHL7 プロジェクト**を右クリックして**参照**] をクリックし、**参照の追加**です。  
  
22. [参照の追加] ダイアログ ボックス、**参照**タブです。**検索対象の**ボックスに移動\<*ドライブ*>: \Program Files\Microsoft BizTalk\<バージョン > Accelerator for HL7\SDK\End エンドツー エンド Tutorial\Tutorial_BTAHL7Drop\Bin です。 をクリックして**Microsoft.Solutions.BTAHL7.HL7Schemas.dll**、 をクリックして**追加**、順にクリック**OK**です。  
  
 進みます[手順 5: スキーマのプロパティを昇格させる](../../adapters-and-accelerators/accelerator-hl7/step-5-promote-schema-properties.md)です。  
  
## <a name="see-also"></a>参照  
 [メッセージの強化のチュートリアル](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)