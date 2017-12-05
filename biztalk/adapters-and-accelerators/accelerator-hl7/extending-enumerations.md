---
title: "列挙型を拡張 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- enumeration values
- 2.X schemas, enumeration values
ms.assetid: 043def35-b644-4502-a2e2-cc1a5fc0328a
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2abb040d79f0c9312a8761289c0bf6252fef2f3a
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="extending-enumerations"></a>列挙型を拡張します。
HL7 メッセージ本文、受信確認、およびメッセージ本文のスキーマで多くのフィールド、セグメント、およびデータ型を指定できる値を確立する列挙体に値を追加することができます。 一般的なテーブル値スキーマ ファイルで作業している HL7 のバージョンについては、特定のテーブル内の値のセットを変更する必要があります (、 **Tablevalues_\<***バージョン* **\>.xsd**スキーマ ファイル)。  
  
 追加する列挙体に、メッセージ ヘッダーのスキーマを別の方法でメッセージのボディ スキーマなどの他のスキーマで行うよりもします。 メッセージ ヘッダー スキーマ用には、MSH_25_GLO_DEF.xsd ファイル内のテーブルを変更する必要があります。 テーブル値のスキーマ ファイル内のテーブルを変更する他のスキーマ (tablevalues_\<バージョン\>.xsd)。  
  
### <a name="to-add-an-enumeration-value-to-the-table-values-common-schema-file"></a>テーブル値の共通スキーマ ファイルに列挙値を追加するには  
  
1.  最初に追加する列挙体を含むテーブルを特定する必要があります。 ソリューション エクスプ ローラーの Visual Studio で、変更する要素が含まれたスキーマ ファイルを開きます。 BizTalk エクスプ ローラーでの値を追加するフィールドの要素をクリックします。  
  
    > [!NOTE]
    >  テーブル値の共通スキーマ ファイル内の列挙型を変更すると、その列挙体を参照するすべてのオブジェクトが影響を受けます。  
  
2.  **プロパティ**ウィンドウ内のテーブルの名前に注意してください、 **Base Data Type**フィールドです。  
  
    > [!NOTE]
    >  テーブルが表示されない場合がある**Base Data Type**フィールド、および**Derived By**プロパティに設定されていない**Restricted**フィールドには、関連付けられている列挙値はありませんし、.  
  
3.  ソリューション エクスプ ローラーで開く、 **Tablevalues_\<***バージョン***\>.xsd**、クリックして**開く**です。  
  
    > [!NOTE]
    >  変更する HL7 スキーマのバージョンごとに個別にこの手順を実行する必要があります。  
  
4.  BizTalk エディターでは、変更、およびそのテーブル ノードをクリックするテーブルを参照します。  
  
5.  [プロパティ] ウィンドウで、**制限**セクションで、をクリックして**列挙**、列挙エディタを開くの省略記号 (...) ボタンをクリックします。  
  
6.  列挙エディターで、既存の値の一覧に新しい値を追加し、をクリックして**OK**です。  
  
### <a name="to-add-an-enumeration-value-to-a-message-header-schema"></a>列挙値をメッセージ ヘッダーのスキーマに追加するには  
  
1.  ソリューション エクスプ ローラーで、MSH_25_GLO_DEF スキーマを開き、をクリックして**開く**です。  
  
2.  右クリックし、 **MSH**に**スキーマ ノードの挿入**、順にクリック**子フィールド要素**です。 [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]MSH と呼ばれるフィールド ノードを追加**フィールド**です。 をクリックして**ENTER**です。  
  
3.  **プロパティ**ウィンドウで、をクリックして、**データ型**ノード、し、ドロップダウン リストから、列挙値を追加するテーブルを選択します。  
  
4.  **プロパティ**ウィンドウで、**制限**セクションで、**列挙**、列挙エディタを開くの省略記号 (...) ボタンをクリックします。  
  
5.  列挙エディターで、既存の値の一覧に新しい値を追加し、をクリックして**OK**です。  
  
     ときに値を追加する任意のノードを列挙するなど、**フィールド**ノード、そのテーブルを使用するすべてのオブジェクトに対してグローバルにその値を追加します。 結果として、これを削除できる、**フィールド**ノード、および値、テーブルの存在されます。 テーブルに BizTalk エディターの右側ウィンドウのスクロールして追加した値の存在を確認するには、これを確認できます。  
  
6.  右クリックし、**フィールド**BizTalk エディターでノードをクリックして**削除**、順にクリック**はい**です。  
  
## <a name="see-also"></a>参照  
 [テーブル値の一般的なスキーマ](../../adapters-and-accelerators/accelerator-hl7/table-values-common-schemas.md)   
 [Z オブジェクトと HL7 2.X スキーマを拡張します。](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md)   
 [宣言されている Z セグメントを作成します。](../../adapters-and-accelerators/accelerator-hl7/creating-declared-z-segments.md)   
 [スキーマでカスタム データ型を作成します。](../../adapters-and-accelerators/accelerator-hl7/creating-custom-data-types-in-schemas.md)   
 [スキーマのカスタム テーブルの作成](../../adapters-and-accelerators/accelerator-hl7/creating-custom-tables-in-schemas.md)   
 [未宣言の Z セグメントの処理](../../adapters-and-accelerators/accelerator-hl7/handling-undeclared-z-segments.md)