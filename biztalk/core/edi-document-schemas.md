---
title: "EDI ドキュメント スキーマ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fc3a30b8-0686-4c06-985b-13f2c95f8e99
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: db79e5e4421719a936f68c409c166f9eac38605c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="edi-document-schemas"></a>EDI ドキュメント スキーマ
ドキュメント スキーマは、EDI トランザクション ドキュメントの種類のボディを定義します。  
  
## <a name="schema-delivery-and-setup"></a>スキーマの配信と設定  
 EDI ドキュメント スキーマは、自己解凍実行可能ファイルに圧縮された状態で配信される[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI\MicrosoftEdiXSDTemplates.exe です。 自己解凍形式の実行可能ファイルによって、確実に、適切なフォルダ構造が作成されることになります (エンコードの種類ごと、およびバージョン/リリースのサブタイプごと)。 実行すると、この実行可能ファイルと同じディレクトリ内のサブフォルダーに、EANCOM、EDIFACT、HIPAA、および X12 のスキーマが展開されます。  
  
 既定のスキーマの名前空間は、次のとおりです。  
  
-   X12 の場合 – `http://schemas.microsoft.com/BizTalk/EDI/X12/2006`  
  
-   EDIFACT の場合 – `http://schemas.microsoft.com/BizTalk/EDI/EDIFACT/2006`  
  
## <a name="schema-naming-convention"></a>スキーマの名前付け規則  
 X12 および EDIFACT エンコードの種類の名前付け規則は\<エンコード > _\<バージョン >\<リリース >\_\<Doctype >。 たとえば、X12 864 ドキュメントの種類 (バージョン 004、リリース 01) の場合は X12_00401_864.xsd スキーマ、EDIFACT AUTHOR ドキュメントの種類 (バージョン D01、リリース C) の場合は EDIFACT_D01C_AUTHOR.xsd スキーマのようになります。  
  
> [!NOTE]
>  EDIFACT スキーマのスキーマ名では、大文字と小文字が区別されます。 たとえば、EFACT_D98B_ORDERS と EFACT_d98B_Orders は 2 つの異なるスキーマです。  
  
## <a name="schema-contents"></a>スキーマ コンテンツ  
 ドキュメント スキーマは、X12 エンコード ドキュメントの場合、ST トランザクション セット ヘッダーで開始し、ST トランザクション セット トレーラーで終了します。 EDIFACT エンコード ドキュメントの場合は、UNH メッセージ ヘッダーで開始し、UNT メッセージ トレーラーで終了します。 スキーマは、これらのヘッダーとトレーラーのデータ要素を定義します。  
  
 ドキュメント スキーマは、次に、トランザクション セット/メッセージ内の各セグメント、およびこれらのセグメント内のデータ要素を定義します。 たとえば、X12_00401_864.xsd スキーマは、BMG セグメントの BMG01、BMG02、および BMG03 要素を定義します。 スキーマは、フィールドの順序、区切り記号の種類、名前空間など、セグメントの複合データ型の特性を指定します。 スキーマのクロス フィールド検証がある場合は、スキーマがそのルールを定義します。 詳細については、次を参照してください。[フィールド セグメントのクロス検証](../core/cross-field-segment-validation.md)です。  
  
 スキーマは、単純データ型、最小出現回数、最小長、および最大長など、セグメント内の各データ要素の特性を指定します。  
  
 ループを含むメッセージの種類である場合、スキーマは、各ループ内のデータ要素、ループの最小出現回数と最大出現回数、ループでの境界の有無などを定義します。 また、セグメントの入れ子や、ループが明示的であるか暗黙的であるかについても、スキーマによって定義されます。  
  
## <a name="see-also"></a>参照  
 [EDI メッセージの構造](../core/edi-message-structure.md)   
 [EDI メッセージの検証](../core/edi-message-validation.md)