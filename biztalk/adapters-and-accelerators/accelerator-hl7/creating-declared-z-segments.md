---
title: "宣言されている Z セグメントを作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Z objects, creating segments
- segments, creating Z segments [Z objects]
- Z segments, creating
- creating, Z segments [Z objects]
ms.assetid: afd1b7b7-089e-4c6a-a063-e708431bb888
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dae9148547f527d29238b6080cd499be8da7b7e6
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
---
# <a name="creating-declared-z-segments"></a>宣言されている Z セグメントを作成します。
(宣言されていない Z セグメント、ボディ部に続く、マルチパーティ メッセージの最後の部分をする必要があります) とは異なり、スキーマの任意のレベルで宣言されている Z セグメントを作成できます。  
  
### <a name="to-create-a-z-segment-in-biztalk-editor"></a>BizTalk エディターで Z セグメントを作成するには  
  
1.  ソリューション エクスプ ローラーの Visual Studio で、クリックして、Z セグメントを追加するスキーマを右クリックして**開く**です。  
  
2.  BizTalk エディターで、スキーマの名前を持つノードを右クリックし、**スキーマ ノードの挿入**、クリックして**子レコード**です。  
  
3.  英数字を 3 桁で、英大文字の"Z"をされている最初の桁で、name の先頭レコードの名前を付けます。 (Z セグメント タグは、次の 3 つの文字を含める必要があります)アンダー スコア (_) を挿入し、セグメントの簡単な説明を追加します。 説明には、1 つまたは一連のスペースを含めずの単語を大文字の各単語の最初の文字を指定する必要があります。 最後の単語は、「セグメント」にする必要があります。 (例では"ZPP_PatientPreferencesSegment)**Enter**キーを押します。  
  
4.  プロパティ ペインで、Z セグメントに必要なプロパティを入力を含む**Data Structure Type** (スキーマ名または xsd:anyType) **Max Occurs**、および**Min Occurs**です。  
  
    > [!NOTE]
    >  レコードのデータ構造体の型を入力すると、子フィールド要素を追加することはできません。  
  
5.  BizTalk エディターでは、Z のセグメントの名前を右クリックし、**スキーマ ノードの挿入**をクリックし、**子フィールド要素**です。  
  
6.  名前から始まる、ピリオドと後にアンダー スコアと、フィールドの簡単な説明、フィールドの数が続くセグメント名の最初の 3 桁、フィールドの名前を入力します。 説明には、1 つまたは一連のスペースを含めずの単語を大文字の各単語の最初の文字を指定する必要があります。 **Enter**キーを押します。  
  
7.  プロパティ ウィンドウで、入力、Z セグメントに必要なプロパティを含む**データ型**、 **Nillable**、**固定**、 **Max Occurs**、および**Min Occurs**です。  
  
8.  コンポーネントでフィールドを作成するには、レコードとしてフィールドを作成し、各コンポーネントについては、そのレコードの子要素を作成します。 これらのサブコンポーネントに、フィールドを作成するには、要素を作成、フィールドとレコードとしてのコンポーネントのサブコンポーネントの子として。 これらのサブコンポーネントは複合データ型であることに注意してください。 たとえば、ZPP_PatientPreferencesSegment をという名前のセグメントをする可能性があります ZPP.1_Dietary フィールドと作成 PD.1 性が高まりますコンポーネント PD.1.1_FoodGroupAllergy サブコンポーネントとします。 PD.1.1_FoodGroupAllergy サブコンポーネントの情報は、単純なデータ型である必要があります。  
  
## <a name="see-also"></a>参照  
 [Z オブジェクトと HL7 2.X スキーマを拡張します。](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md)   
 [スキーマでカスタム データ型を作成します。](../../adapters-and-accelerators/accelerator-hl7/creating-custom-data-types-in-schemas.md)   
 [スキーマのカスタム テーブルの作成](../../adapters-and-accelerators/accelerator-hl7/creating-custom-tables-in-schemas.md)   
 [列挙型を拡張します。](../../adapters-and-accelerators/accelerator-hl7/extending-enumerations.md)   
 [未宣言の Z セグメントの処理](../../adapters-and-accelerators/accelerator-hl7/handling-undeclared-z-segments.md)