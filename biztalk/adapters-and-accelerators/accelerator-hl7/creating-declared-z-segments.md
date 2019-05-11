---
title: 宣言された Z セグメントの作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Z objects, creating segments
- segments, creating Z segments [Z objects]
- Z segments, creating
- creating, Z segments [Z objects]
ms.assetid: afd1b7b7-089e-4c6a-a063-e708431bb888
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 67b6469130173dbdc60d223f4f5c4f268699ce3f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65255637"
---
# <a name="creating-declared-z-segments"></a>宣言された Z セグメントの作成
(宣言されていない Z セグメント、マルチパーティ メッセージのボディ部を次の最後の部分である必要があります) とは異なり、スキーマの任意のレベルで宣言された Z セグメントを作成できます。  
  
### <a name="to-create-a-z-segment-in-biztalk-editor"></a>Z セグメントを BizTalk エディターで作成するには  
  
1.  ソリューション エクスプ ローラーの Visual Studio で、クリックして Z セグメントを追加するスキーマを右クリックして**オープン**します。  
  
2.  BizTalk エディターでスキーマの名前を持つノードを右クリックし、[**スキーマ ノードの挿入**、] をクリックし、**子レコード**します。  
  
3.  名前を 3 桁の英数字、大文字で"Z"されている最初の桁で始まるレコードの名前を付けます。 (Z セグメントのタグは、次の 3 つの文字を含める必要があります)アンダー スコア (_) を挿入し、セグメントの簡単な説明を追加します。 説明には、1 つまたは一連のスペースを含めずの単語を大文字で入力の各単語の最初の文字を指定する必要があります。 最後の単語には、「セグメント」必要があります。 (例では"ZPP_PatientPreferencesSegment)**Enter**キーを押します。  
  
4.  プロパティ ペインで、Z セグメントの必要なプロパティを入力を含む**Data Structure Type** (スキーマ名または xsd:anyType) **Max Occurs**、および**Min Occurs**します。  
  
    > [!NOTE]
    >  レコードのデータ構造体の型を入力する場合、子フィールド要素を追加することができなきます。  
  
5.  BizTalk エディターでは、Z セグメントの名前を右クリックし、[**スキーマ ノードの挿入**、] をクリックし、**子フィールド要素**します。  
  
6.  名前から始まる、ピリオド、アンダー スコアと、フィールドの簡単な説明が続く、フィールドの電話番号、セグメント名の最初の 3 つの数字、フィールドの名前を入力します。 説明には、1 つまたは一連のスペースを含めずの単語を大文字で入力の各単語の最初の文字を指定する必要があります。 **Enter**キーを押します。  
  
7.  プロパティ ペインで、Z セグメントの必要なプロパティを入力を含む**データ型**、 **Nillable**、**固定**、 **Max Occurs**、**Min Occurs**します。  
  
8.  コンポーネントと、フィールドを作成するには、レコードとフィールドを作成し、コンポーネントごとにそのレコードの子要素を作成します。 サブコンポーネントのフィールドを作成するには、要素を作成、フィールドとレコードとしてコンポーネントとサブコンポーネントの子として。 サブコンポーネントの複合データ型であることに注意してください。 たとえば、ZPP_PatientPreferencesSegment という名前のセグメントの可能性がありますを作成 ZPP.1_Dietary フィールドと PD.1 アレルギー コンポーネント PD.1.1_FoodGroupAllergy サブコンポーネントとします。 PD.1.1_FoodGroupAllergy サブコンポーネントには、単純なデータ型である必要があります。  
  
## <a name="see-also"></a>参照  
 [Z オブジェクト HL7 2.X スキーマの拡張](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md)   
 [スキーマでカスタム データ型の作成](../../adapters-and-accelerators/accelerator-hl7/creating-custom-data-types-in-schemas.md)   
 [スキーマのカスタム テーブルの作成](../../adapters-and-accelerators/accelerator-hl7/creating-custom-tables-in-schemas.md)   
 [列挙の拡張](../../adapters-and-accelerators/accelerator-hl7/extending-enumerations.md)   
 [未宣言の Z セグメントの処理](../../adapters-and-accelerators/accelerator-hl7/handling-undeclared-z-segments.md)