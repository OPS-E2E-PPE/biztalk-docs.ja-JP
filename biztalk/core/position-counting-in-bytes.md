---
title: 位置のカウント (バイト単位) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5cf666ec-d15e-4d2d-9df9-49189f352c65
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5801987517d66147a9c8110c945b8fdff84bc88b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396226"
---
# <a name="position-counting-in-bytes"></a>位置のカウント (バイト単位)

## <a name="overview"></a>概要

使用することができます、**カウント位置 (バイト単位)** のプロパティ、**スキーマ**ノード。 

* 値の入力方法の指定、**位置指定値**と**位置指定オフセット**位置指定レコード内のさまざまなフィールドのプロパティが解釈されます
* 値の入力方法の指定、**タグ オフセット**位置指定レコード自体のプロパティが解釈されます

既定では、これらの値が文字数として解釈されます。 しかし、**カウント位置 (バイト単位)** プロパティに設定されて**True**、これらの値はバイト数として解釈されます。  
  
 設定、**カウント位置 (バイト単位)** プロパティを**True**がマルチバイト文字を扱うときに必要な設定 (MBCS や DBCS) データ、または、SAP、メインフレームで、フラット ファイル メッセージが生成されるときに、または位置のバイト単位でカウントされる可能性が他のシステムです。  
  
 フィールドの長さ (バイト単位) をカウントする複雑な文字をエンコードするために使用バイト数が変数、および、フィールド境界の決定に関していくつかの問題が発生することができます。 フラット ファイル逆アセンブラーは、このような状況でフラット ファイルを解析し、使用中で文字エン コードの知識に基づく適切に解析を行って決定しようとします。  
  
 この型の意思決定の解析の例では、先行バイト MBCS 文字エン コードに関するものです。 先頭バイトは、既知のバイト値のマルチバイト文字エン コードの開始に使用して、独自でこれを実行することはありません。 文字ではなくバイトを使用してフィールドの長さを指定すると、フィールドの最後のバイトがあるが単独で全体の文字を構成することはできません、先行バイトを使用する状況が発生します。 このような場合は、フラット ファイル逆アセンブラーは、前のフィールドの最後の文字として先行バイトの直前に現れた文字を扱うし、先行バイトで始まる次のフィールドの解析を開始します。  

これらのプロパティについて詳しく[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。 
  
## <a name="see-also"></a>参照  
 [位置指定レコードに関する注意](../core/positional-record-considerations.md)   
