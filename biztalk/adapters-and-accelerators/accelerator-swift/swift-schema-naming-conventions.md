---
title: SWIFT スキーマの名前付け規則 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- naming conventions [schemas]
- schemas, naming conventions
ms.assetid: 3c1f2519-2575-4178-89c1-e97333c1e6bd
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f173b1d2e424a111e4657c0b0d943aee932ac21b
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529743"
---
# <a name="swift-schema-naming-conventions"></a>SWIFT スキーマの名前付け規則
Microsoft[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]社会の BizTalk エディターを使用して作成された世界銀行間金融電気通信 (SWIFT) FIN メッセージのスキーマが含まれています。 これらのスキーマは、全体では、次の規則に準拠しています。  
  
> [!NOTE]
>  すべてのスキーマは、バージョン管理されます。 バージョンを表示、開く[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、ソリューション エクスプ ローラーでスキーマを右クリックします。 \<スキーマ\>標準バージョン プロパティまでのプロパティ ウィンドウのスクロールで BizTalk エディターを選択したノード。  
  
- 各インターチェンジのスキーマ ファイルの名前は**MT*xxx*.xsd**ここで、 *xxx* FIN メッセージの種類です。  
  
- 各メッセージに関連するマスター ポリシー ファイルの名前は**MT*xxx*_Master_Policy.xml**、ビジネス ルール エンジン (BRE) に対応する名前が、 **MT*xxx*_Master_Policy**、リスト名を持つ**MT*xxx*_PolicyList**します。  
  
- 各メッセージに関連付けられている検証ポリシー ファイルの名前は**MT*xxx*_Validation_Policy.xml**、BRE に対応する名前が、 **MT*xxx*_Validation_Policy**します。  
  
- ルートの名前は、各メッセージ スキーマ内で**SWIFT_CATEGORY*z*_MT*zxx*_Interchange**ここで、 *z*は、メッセージ カテゴリ (メッセージの種類の最初の桁) と*zxx*は、メッセージ型です。  
  
- 各メッセージ スキーマのターゲット名前空間は**<http://schemas.microsoft.com/BizTalk/Solutions/FinancialServices/SWIFT/Category*z*/MT*zxx>**<em>ここで、* z</em>メッセージ カテゴリ (メッセージの種類の最初の桁) と*zxx*はメッセージの種類。  
  
- ドキュメントの種類が**MT * zxx**<em>ここで、* zxx</em>は、メッセージ型です。  
  
- 番号付けされていないフィールドとサブ フィールドの名前には、ビジネスのわかりやすい名前が含まれます。 各単語の最初の文字が大文字になっているし、余分な空白または句読点の単語、名前が含まれません (たとえば、名前になります**ServiceIdentifier**ではなく、**サービス識別子**).  
  
- 準拠しているメッセージ内のシーケンスのラベル、 *SWIFT リファレンス ガイド*(たとえば、 **SequenceA**)。  
  
- 番号付き SWIFT フィールドのラベル、番号コードと省略可能な文字の書式設定後に続くシーケンス (ある場合)、わかりやすいタイトルを含める (たとえば、 **Reference_A_20C**)。  
  
- ノードのラベルは、さまざまなフィールドの複数の形式では、  **\<*選択肢*\>**、し、各オプションは、番号付きフィールドと (たとえば、**日付_A_98A**と**DateTime_A_98C**)。  
  
- サブ フィールドの最下位レベルの要素定義の名前が続くサブ フィールドの名前から成る**型**(たとえば、 **accountType**アカウントの)。  
  
  メッセージのスキーマで他の名前空間を以下に示します。  
  
- xmlns:xs="<http://www.w3.org/2001/XMLSchema>". これは、既定の W3C XML スキーマ名前空間です。  
  
- xmlns:b="<http://schemas.microsoft.com/BizTalk/2003>". これは、既定の BizTalk 名前空間です。  
  
  各メッセージ スキーマは、基本型と一般的なデータ型のスキーマを直接参照します。  
  
## <a name="see-also"></a>参照  
 [スキーマの操作](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md)