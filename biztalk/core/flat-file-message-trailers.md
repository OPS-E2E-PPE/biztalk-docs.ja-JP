---
title: フラット ファイル メッセージのトレーラー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cfe115a5-4fdc-4779-94f3-437b5a06fbd4
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d0f609ee7e4770fdc6f34bcd2ff8c11e5f10b6e4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65345366"
---
# <a name="flat-file-message-trailers"></a>フラット ファイル メッセージのトレーラー
フラット ファイル インスタンス メッセージのヘッダーとで構成したフラット ファイル スキーマで、フラット ファイル逆アセンブラーでは、省略可能なフラット ファイル インスタンス メッセージ トレーラーの解析が制御される、**トレーラー スキーマ**デザイン時フラット ファイル逆アセンブラーのプロパティまたは**XMLNORM します。TrailerSpecName**メッセージ コンテキスト プロパティ。 これら 2 つのメソッドのいずれかを使用してスキーマが指定されていない場合、フラット ファイル逆アセンブラーは、フラット ファイル インスタンス メッセージにトレーラーが含まれていないと想定されます。  
  
 フラット ファイル インスタンスに関連付けられたメッセージ コンテキストにデータの個々 の項目をコピーする、プロパティの昇格が使用することもできませんとは異なり、フラット ファイル インスタンス メッセージ ヘッダーのフラット ファイル インスタンス メッセージのトレーラーも保存でき、1 つの単位として復元メッセージの本文。 適切なスキーマを指定することでトレーラーを送信フラット ファイル インスタンス メッセージに追加するただし、**トレーラー スキーマ**フラット ファイル アセンブラーのデザイン時プロパティまたは**XMLNORM します。TrailerSpecName**メッセージ コンテキスト プロパティ。 プロパティを降格、メッセージ コンテキストからフラット ファイル インスタンス メッセージの本文のか、対応するスキーマの既定値または固定値を指定することによって、トレーラーの可変部分を構成するデータを指定できます。  
  
## <a name="see-also"></a>参照  
 [フラット ファイル メッセージのヘッダー](../core/flat-file-message-headers.md)   
 [フラット ファイル メッセージの本文](../core/flat-file-message-bodies.md)   
 [フラット ファイル メッセージの構造](../core/structure-of-a-flat-file-message.md)   
 [フラット ファイル メッセージのスキーマを作成する方法](../core/how-to-create-schemas-for-flat-file-messages.md)