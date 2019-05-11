---
title: フィールドの妥当性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 04380208-9bfd-43cf-a279-104daea2b978
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f6ddea01774cdae6fb17c27212f2d53351fa072
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65345578"
---
# <a name="field-justification"></a>フィールドの位置揃え

## <a name="overview"></a>概要
フィールドのデータの文字にする前に発生するかどうかに関係するフィールドの位置揃え (左揃え) または後 (右揃え)、埋め込み文字に付属します。  
  
 場合によってフィールド内に含まれるデータの文字では、そのフィールドに専用の領域をすべて必要はありません。 これは、によって決定されるバイト数またはフィールドに割り当てられる文字の数が固定の位置指定レコードで最も頻繁には true、**位置指定値**と**位置指定オフセット**プロパティ。 データの項目が埋め込み文字が挿入されているフィールドの未使用の部分で、フィールドの長さより小さいこと、このようなシナリオで一般的です。  
  
 このような埋め込みは、区切られたレコードにも発生時の値、**埋め込み文字を含めた最小値**プロパティは、データの関連する項目を格納するために必要な領域を超えています。  
  
 両方このような場合の値、 **Justification**プロパティ (**左**または**右**) の関連**フィールド要素**または**フィールド属性**ノードが埋め込み文字が、データの文字 (左揃え) に従うかどうか、または埋め込み文字は (右揃え)、データ文字の前にするかどうかを判断します。  
  
 フラット ファイル逆アセンブラーは、フラット ファイル インスタンス メッセージを同等の XML インスタンス メッセージに変換されるとき、 **Justification**プロパティは、対応するフィールドを解析するときに使用されます。 フラット ファイル アセンブラーが、同等のフラット ファイル インスタンス メッセージに XML インスタンス メッセージを変換するときに、**理由**プロパティを使用して、存在する場合と、埋め込み文字が特定のフィールドに関連付けられたを確認します。データ ストリームに追加する必要があります。 前または後、対応するデータの文字。  
  
## <a name="see-also"></a>参照  
- [フィールドに関する注意](../core/field-considerations.md)   
- 詳細については、次のプロパティで[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]:  
    - 位置揃え (フラット ファイル スキーマのノード プロパティ)  
    - 位置指定オフセット (フラット ファイル スキーマのノード プロパティ)  
    - 位置指定値 (フラット ファイル スキーマのノード プロパティ)