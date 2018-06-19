---
title: フラット ファイル メッセージのトレーラー |Microsoft ドキュメント
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
ms.openlocfilehash: 7cbeaef3f23de3cb89d873413964cd331ec23f43
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246290"
---
# <a name="flat-file-message-trailers"></a>フラット ファイル メッセージのトレーラー
フラット ファイル インスタンス メッセージのヘッダーのフラット ファイル逆アセンブラーでは、省略可能なフラット ファイル インスタンス メッセージ トレーラーの解析で構成したフラット ファイル スキーマによって制御されるよう、**トレーラー スキーマ**デザイン時フラット ファイル逆アセンブラーのプロパティまたは**XMLNORM です。TrailerSpecName**メッセージ コンテキスト プロパティです。 いずれかの方法を使用してスキーマを指定しなかった場合、フラット ファイル逆アセンブラーは、フラット ファイル インスタンス メッセージにトレーラーが含まれないと見なします。  
  
 フラット ファイル インスタンス メッセージのヘッダーとは異なり、フラット ファイル インスタンス メッセージのトレーラーは、1 つの単位として保存および復元できません。また、プロパティの昇格を使用して、フラット ファイル インスタンス メッセージの本文に関連付けられているメッセージ コンテキストにデータの各項目をコピーすることもできません。 ただし、トレーラーに追加できます送信フラット ファイル インスタンス メッセージ内の適切なスキーマを指定することによって、**トレーラー スキーマ**、フラット ファイル アセンブラーのデザイン時プロパティまたは**XMLNORM です。TrailerSpecName**メッセージ コンテキスト プロパティです。 トレーラーの可変部分を構成するデータは、フラット ファイル インスタンス メッセージの本文のメッセージ コンテキストからプロパティを降格することにより指定できます。または、対応するスキーマの既定値 (あるいは固定値) でも指定できます。  
  
## <a name="see-also"></a>参照  
 [フラット ファイル メッセージのヘッダー](../core/flat-file-message-headers.md)   
 [フラット ファイル メッセージの本文](../core/flat-file-message-bodies.md)   
 [フラット ファイル メッセージの構造](../core/structure-of-a-flat-file-message.md)   
 [フラット ファイル メッセージのスキーマを作成する方法](../core/how-to-create-schemas-for-flat-file-messages.md)