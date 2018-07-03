---
title: 区切られたレコードの処理をタグ付け |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 568eb804-bea5-46d4-8547-8bc30b87156c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c50a3daad9bb77ba4a9cbc264f018e29601edfff
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972467"
---
# <a name="tag-handling-in-delimited-records"></a>タグで区切られたレコードの処理

## <a name="overview"></a>概要
区切られたレコードには、レコードの種類を明確に区別するための、タグという文字列が含まれています。 これにより、適切なを正しく識別するためにフラット ファイル逆アセンブラー**レコード**フラット ファイル レコードを正しく解析に必要な情報を含むスキーマのノード。  

 使用することができます、**タグ識別子**区切られたレコードでタグを指定するプロパティ。 位置指定レコードのタグとは異なり、区切られたレコードのタグは、区切られたレコードの先頭に設定されている必要があります。また、等価な XML 形式に変換される際、タグはデータから自動的に除外されます。  

## <a name="see-also"></a>参照  
- [区切り記号付きレコードに関する注意](../core/delimited-record-considerations.md)   
- **タグ識別子 (フラット ファイル スキーマのノード プロパティ)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
