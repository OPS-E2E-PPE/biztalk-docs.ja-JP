---
title: "位置揃えのフィールド |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 04380208-9bfd-43cf-a279-104daea2b978
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da9209040e64380b3a7a167dd013a15232543a75
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="field-justification"></a>フィールドの位置揃え

## <a name="overview"></a>概要
フィールドの位置揃えは、フィールド データの文字が埋め込み文字の前 (左揃えの場合) に出現するか、後 (右揃えの場合) に出現するかを制御します。  
  
 フィールドに含まれるデータの文字数が、そのフィールドに割り当てられている領域と必ずしも一致するとは限りません。フィールドの領域が余る場合もあります。 これは、によって決定されるバイト数またはフィールドに割り当てられる文字数が固定の位置指定レコードで最も頻繁には true、**位置指定値**と**位置指定オフセット**プロパティです。 データ項目がフィールド長よりも短い場合、使用されないフィールド領域には、埋め込み文字が挿入されます。  
  
 このような埋め込みは区切られたレコードにも発生するときの値、**埋め込み文字を含めた最小の長さ**プロパティは、データの関連する項目を格納するために必要な領域を超えています。  
  
 両方このような場合の値、 **Justification**プロパティ (**左**または**右**) の関連**フィールド要素**または**Field 属性**ノードは、埋め込み文字が、データの文字 (左揃え) を後ろするかどうか、または埋め込み文字は (右揃え)、データ文字の前にするかどうかを決定します。  
  
 同等の XML インスタンス メッセージに、フラット ファイル逆アセンブラーがフラット ファイル インスタンス メッセージを変換するときに、 **Justification**プロパティは、対応するフィールドを解析するときに使用します。 フラット ファイル アセンブラーが、同等のフラット ファイル インスタンス メッセージに XML インスタンス メッセージを変換するときに、 **Justification**と埋め込み文字に関連付けられている特定のフィールドでは、存在する場合を決定するプロパティを使用データ ストリームに追加する必要があります。 前に、または対応するデータの文字の後にします。  
  
## <a name="see-also"></a>参照  
- [フィールドに関する考慮事項](../core/field-considerations.md)   
- 詳細については、次のプロパティで[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]:  
    - 位置揃え (フラット ファイル スキーマのノード プロパティ)  
    - 位置指定オフセット (フラット ファイル スキーマのノード プロパティ)  
    - 位置指定値 (フラット ファイル スキーマのノード プロパティ)