---
title: フラット ファイル メッセージのヘッダー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1981daaf-149a-426d-9a2f-5fcf64bce185
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1e4914bb5efa806cc16072b6beb96c4d53f6e7ec
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387917"
---
# <a name="flat-file-message-headers"></a>フラット ファイル メッセージのヘッダー
構成したフラット ファイル スキーマによって制御されますが、フラット ファイル逆アセンブラーでは、省略可能なフラット ファイル インスタンス メッセージ ヘッダーの解析、**ヘッダー スキーマ**フラット ファイル逆アセンブラーのデザイン時プロパティまたは**XMLNORM します。HeaderSpecName**メッセージ コンテキスト プロパティ。 これら 2 つのメソッドのいずれかを使用してスキーマが指定されていない場合、フラット ファイル逆アセンブラー、フラット ファイル インスタンス メッセージにヘッダーが含まれていないこと前提としています。  

## <a name="outbound-messages"></a>送信メッセージ  
 内の適切なスキーマを指定することで、ヘッダーを生成するために、フラット ファイル アセンブラーを構成する送信フラット ファイル インスタンス メッセージの場合、その**ヘッダー仕様名**デザイン時プロパティまたは**XMLNORM します。HeaderSpecName**メッセージ コンテキスト プロパティ。 メッセージ コンテキスト プロパティを設定する方法についての詳細については、次を参照してください。**メッセージ コンテキスト プロパティ**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。  

## <a name="inbound-messages"></a>受信メッセージ  
 受信フラット ファイル インスタンス メッセージのヘッダー内のデータを空白を保持し、2 つの方法で使用されることができます。 最初に、フラット ファイル インスタンス メッセージのヘッダーは、対応する送信フラット ファイル インスタンス メッセージのヘッダーとして後で復元の本文のメッセージ コンテキスト内で完全に保存できます。 使用することができます、 **Preserve ヘッダー**ヘッダーを保持することを指定する受信パイプラインのプロパティ。 保存したヘッダーが送信メッセージで使用される場合は、ヘッダーがフラット ファイル アセンブラーで指定します。  
  
 フラット ファイル インスタンス メッセージのヘッダーからのデータの第 2 に、個々 のアイテムは、対応するスキーマのフィールドの 1 つ以上のプロパティの昇格を指定することで、フラット ファイル メッセージの本文に関連付けられているメッセージ コンテキストにコピーできます。 プロパティの昇格の詳細については、次を参照してください。[プロパティの昇格](../core/promoting-properties.md)します。  
  
## <a name="see-also"></a>参照  
 [フラット ファイル メッセージの本文](../core/flat-file-message-bodies.md)   
 [フラット ファイル メッセージのトレーラー](../core/flat-file-message-trailers.md)   
 [フラット ファイル メッセージの構造](../core/structure-of-a-flat-file-message.md)   
 [フラット ファイル メッセージのスキーマを作成する方法](../core/how-to-create-schemas-for-flat-file-messages.md)