---
title: "名前付け規則に SWIFT のスキーマ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- naming conventions [schemas]
- schemas, naming conventions
ms.assetid: 3c1f2519-2575-4178-89c1-e97333c1e6bd
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: beb792fe66e5806a186b0ffb946aa99f86a6a10c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="swift-schema-naming-conventions"></a>SWIFT スキーマの名前付け規則
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] Society の BizTalk エディターを使用して作成された世界銀行間財務通信 (SWIFT) FIN メッセージのスキーマが含まれています。 これらのスキーマは、全体で、次の規則に従います。  
  
> [!NOTE]
>  すべてのスキーマをバージョン管理します。 バージョンを表示、開く[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、し、ソリューション エクスプ ローラーでスキーマを右クリックします。 \<スキーマ > ノードをプロパティ ウィンドウのスクロール標準バージョン プロパティの BizTalk エディターを選択します。  
  
-   各インターチェンジのスキーマ ファイルの名前は **MT*xxx** *、.xsd、 *xxx* FIN メッセージ型です。  
  
-   各メッセージに関連するマスター ポリシー ファイルの名前は **MT*xxx*_Master_Policy.xml**、ビジネス ルール エンジン (BRE) に対応する名前が、  **MT*xxx*_Master_Policy**の一覧の名前を持つ **MT*xxx*_PolicyList * *。  
  
-   各メッセージに関連付けられている検証ポリシー ファイルの名前は **MT*xxx*_Validation_Policy.xml**、BRE に対応する名前が、  **MT*xxx*_Validation_Policy**です。  
  
-   ルートの名前は、各メッセージ スキーマ内で **SWIFT_CATEGORY*z*_MT*zxx** *、_Interchange 場所*z*メッセージ カテゴリには(メッセージの種類の最初の数字) と*zxx*は、メッセージ型です。  
  
-   各メッセージ スキーマのターゲット名前空間は **http://schemas.microsoft.com/BizTalk/Solutions/FinancialServices/SWIFT/Category*z*/MT*zxx** *、どこで*z*メッセージ カテゴリ (メッセージの種類の最初の桁) と*zxx*は、メッセージの種類。  
  
-   ドキュメントの種類が **MT*zxx** *、どこで*zxx*は、メッセージ型です。  
  
-   番号付けされていないフィールドと下位のフィールドの名前には、ビジネスのわかりやすい名前が含まれます。 各単語の最初の文字を大文字にすると、し、余分な空白や句読点単語間の名前が含まれません (たとえば、名前がなります**ServiceIdentifier**ではなく、**サービス識別子**).  
  
-   準拠しているメッセージ内のシーケンスのラベル、 *SWIFT リファレンス ガイド*(たとえば、 **SequenceA**)。  
  
-   番号付き SWIFT のフィールドのラベルの後に番号と省略可能な文字書式続くシーケンス (存在する場合)、わかりやすいタイトルを含める (たとえば、 **Reference_A_20C**)。  
  
-   ノードのラベルは、フィールドの複数の形式の選択では、   **\<*選択肢*> * *、し、各オプションは、番号付きフィールドと (たとえば、 **Date_A_98A**と**DateTime_A_98C**)。  
  
-   サブ フィールドの最も低いレベルの要素の定義の名前は、続いてサブ フィールドの名前で構成されます**型**(たとえば、 **accountType**アカウント用)。  
  
 他の名前空間、メッセージ スキーマで、次のとおりです。  
  
-   xmlns:xs ="http://www.w3.org/2001/XMLSchema"です。 これは、既定の W3C XML スキーマ名前空間です。  
  
-   xmlns:b"http://schemas.microsoft.com/BizTalk/2003"を = です。 これは、既定の BizTalk 名前空間です。  
  
 各メッセージ スキーマは、基本型と一般的なデータ型のスキーマを直接参照します。  
  
## <a name="see-also"></a>参照  
 [スキーマの操作](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md)