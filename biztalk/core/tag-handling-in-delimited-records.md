---
title: "区切られたレコードの処理をタグ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 568eb804-bea5-46d4-8547-8bc30b87156c
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5be9d28e3de6b1a7613db8d0c5ac7365a298a679
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="tag-handling-in-delimited-records"></a>区切られたレコードのタグ処理

## <a name="overview"></a>概要
区切られたレコードには、レコードの種類を明確に区別するための、タグという文字列が含まれています。 こうと、適切なを正しく識別するフラット ファイル逆アセンブラー**レコード**フラット ファイル レコードを正しく解析に必要な情報を含むスキーマのノードです。  
  
 使用することができます、**タグ識別子**区切られたレコード内のタグを指定するプロパティです。 位置指定レコードのタグとは異なり、区切られたレコードのタグは、区切られたレコードの先頭に設定されている必要があります。また、等価な XML 形式に変換される際、タグはデータから自動的に除外されます。  
  
## <a name="see-also"></a>参照  
-  [区切り記号付きレコードに関する注意点](../core/delimited-record-considerations.md)   
-  **タグ識別子 (フラット ファイル スキーマのノード プロパティ)**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]