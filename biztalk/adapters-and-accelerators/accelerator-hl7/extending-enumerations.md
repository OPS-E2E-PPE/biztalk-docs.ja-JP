---
title: 列挙の拡張 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- enumeration values
- 2.X schemas, enumeration values
ms.assetid: 043def35-b644-4502-a2e2-cc1a5fc0328a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 60e8e5ab2b5072679e9d29f1c13f58c554e41c93
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65268058"
---
# <a name="extending-enumerations"></a>列挙の拡張
HL7 メッセージの本文、受信確認、およびメッセージ本文のスキーマのフィールド、セグメント、およびデータのさまざまな種類の値を確立するための列挙体には、値を追加できます。 ユーザーが作業して、HL7 バージョン用の一般的なテーブル値スキーマ ファイルの特定のテーブル内の値のセットを変更する必要があります (、 **Tablevalues_\<**<em>バージョン</em> **\>.xsd**スキーマ ファイル)。  
  
 追加する列挙体にメッセージのヘッダー スキーマ用の別の方法でメッセージ本文のスキーマなどの他のスキーマの場合。 メッセージ ヘッダー スキーマ、MSH_25_GLO_DEF.xsd ファイル内のテーブルを変更する必要があります。 テーブル値のスキーマ ファイル内のテーブルを変更する他のスキーマ (tablevalues_\<バージョン\>.xsd)。  
  
### <a name="to-add-an-enumeration-value-to-the-table-values-common-schema-file"></a>テーブル値の一般的なスキーマ ファイルに列挙値を追加するには  
  
1. 最初に追加する列挙体を含むテーブルを決定する必要があるとします。 ソリューション エクスプ ローラーの Visual Studio で、変更する要素が含まれているスキーマ ファイルを開きます。 BizTalk エクスプローラで、フィールド要素の値を追加する をクリックします。  
  
   > [!NOTE]
   >  テーブル値の一般的なスキーマ ファイル内の列挙型を変更すると、その列挙体を参照するすべてのオブジェクトが影響を受けます。  
  
2. **プロパティ**ウィンドウ内のテーブルの名前に注意してください、 **Base Data Type**フィールド。  
  
   > [!NOTE]
   >  テーブルが表示されない場合がある**Base Data Type**フィールド、および**Derived By**プロパティに設定されていない**Restricted**フィールドには、関連付けられている列挙体にありません.  
  
3. ソリューション エクスプ ローラーで開く、 **Tablevalues_\<**<em>バージョン</em>**\>.xsd**、 をクリックし、**開く**します。  
  
   > [!NOTE]
   >  変更する HL7 スキーマのバージョンごとに個別にこの手順を実行する必要があります。  
  
4. BizTalk エディターでは、変更、およびそのテーブル ノードをクリックするテーブルを参照します。  
  
5. プロパティ ウィンドウで、**制限**セクションで、**列挙**、列挙エディターを開く省略記号 (...) ボタンを順にクリックします。  
  
6. 列挙エディターで、既存の値の一覧に新しい値を追加し、順にクリックします**OK**します。  
  
### <a name="to-add-an-enumeration-value-to-a-message-header-schema"></a>列挙値をメッセージ ヘッダーのスキーマに追加するには  
  
1. ソリューション エクスプ ローラーで、MSH_25_GLO_DEF スキーマを開くし、順にクリックします**開く**します。  
  
2. 右クリックし、 **MSH**に**スキーマ ノードの挿入**、 をクリックし、**子フィールド要素**します。 [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] 呼ばれる MSH フィールド ノードを追加**フィールド**します。 クリックして**ENTER**します。  
  
3. **プロパティ**ウィンドウで、をクリックして、**データ型**ノードのドロップダウン リストから、列挙値を追加するテーブルを選択します。  
  
4. **プロパティ**ウィンドウで、**制限**セクションで、**列挙**、列挙型のエディターを開く省略記号 (...) ボタンを順にクリックします。  
  
5. 列挙エディターで、既存の値の一覧に新しい値を追加し、順にクリックします**OK**します。  
  
    追加すると、値の列挙の任意のノードなど、**フィールド**ノードで、そのテーブルを使用するすべてのオブジェクトのグローバルにその値を追加します。 その結果、これを削除できる、**フィールド**ノード、および値テーブルに存在するされます。 これを確認するには、テーブルに BizTalk エディターの右側ウィンドウのスクロールを追加した値が存在することを確認します。  
  
6. 右クリックし、**フィールド**BizTalk エディターでノードをクリックして**削除**、順にクリックします**はい**します。  
  
## <a name="see-also"></a>参照  
 [テーブル値の一般的なスキーマ](../../adapters-and-accelerators/accelerator-hl7/table-values-common-schemas.md)   
 [Z オブジェクト HL7 2.X スキーマの拡張](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md)   
 [宣言された Z セグメントの作成](../../adapters-and-accelerators/accelerator-hl7/creating-declared-z-segments.md)   
 [スキーマでカスタム データ型の作成](../../adapters-and-accelerators/accelerator-hl7/creating-custom-data-types-in-schemas.md)   
 [スキーマのカスタム テーブルの作成](../../adapters-and-accelerators/accelerator-hl7/creating-custom-tables-in-schemas.md)   
 [未宣言の Z セグメントの処理](../../adapters-and-accelerators/accelerator-hl7/handling-undeclared-z-segments.md)