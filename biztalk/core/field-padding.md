---
title: フィールドの埋め込み |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 47017036-7d64-4222-b574-d2913bf69358
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a4eac7354d7e867ceca759caa40098ef09ed2a2d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388150"
---
# <a name="field-padding"></a>フィールドのパディング

## <a name="overview"></a>概要

埋め込み文字は、データが文字またはフィールドに予約されたバイト数よりも小さいフィールド内に含まれるときに、区切られたと位置指定レコード内のフィールドで使用されます。 これらの文字は、存在する場合に、データを必要としないフィールドの一部を占有します。 使用して、フィールドの単位で指定された埋め込み文字、**埋め込み文字**と**埋め込み文字の種類**プロパティの対応する**フィールド要素**と**フィールド属性**ノード。 特定のフィールドを既定の埋め込み文字の埋め込み文字が指定されていない場合は、スペース ("")、そのフィールドに使用します。  
  
## <a name="inbound-instances"></a>受信インスタンス
 先頭または末尾の指定したインスタンスまたは特定のフィールドの既定の埋め込み文字、インスタンス メッセージは受信インスタンス メッセージの場合、特定のレコードは、位置指定ベースか、区切られているかどうかに関係なく、フラット ファイル逆アセンブラーを破棄します。等価な XML 形式に変換されます。 先頭または末尾の破棄された埋め込み文字のインスタンスかどうかに依存、 **Justification** 、対応するプロパティ**フィールド要素**と**フィールド属性**にノードが設定されている**右**または**左**、それぞれします。  

## <a name="outbound-instances"></a>送信インスタンス  
 送信インスタンス メッセージの場合は、フラット ファイル アセンブラーに挿入されます、適切な数の指定、または既定の埋め込み文字のフィールド、フィールドの長さが正しくなるよう。 前に、または後、データ文字かどうかに基づいて、埋め込み文字が挿入される、 **Justification**プロパティの対応する**フィールド要素**と**フィールド属性**にノードが設定されている**右**または**左**、それぞれします。  
  
 送信インスタンス メッセージに埋め込まれているフィールドが位置指定レコード内に含まれるときに、**位置指定オフセット**と**位置指定値**プロパティの対応する**フィールド要素**または**フィールド属性**埋め込み文字が必要かどうかと、そうである場合を決定する、フィールドに格納する必要があります、データ文字の数と組み合わせて、ノード数。 埋め込み文字はのみに、送信インスタンス メッセージに埋め込まれているフィールドは、区切られたレコード内に含まれる、ときに挿入されたときの値、**埋め込み文字を含めた最小値**プロパティの対応する**フィールド要素**または**フィールド属性**ノードは、データの文字数を超えています。  

## 
これらのプロパティについて詳しく[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。

## <a name="see-also"></a>参照  
 [フィールドに関する考慮事項](../core/field-considerations.md)   
 [フィールドの位置揃え](../core/field-justification.md)   
 [位置指定レコードにおけるフィールド位置の仕様](../core/specification-of-field-positions-within-positional-records.md)  