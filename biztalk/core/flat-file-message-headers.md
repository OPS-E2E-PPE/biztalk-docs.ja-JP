---
title: フラット ファイル メッセージのヘッダー |Microsoft ドキュメント
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
ms.openlocfilehash: 271e9fe74d0a55f4b3ff5271861d24474fffaf37
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246354"
---
# <a name="flat-file-message-headers"></a>フラット ファイル メッセージのヘッダー
構成したフラット ファイル スキーマによって制御されますが、フラット ファイル逆アセンブラーでは、省略可能なフラット ファイル インスタンス メッセージ ヘッダーの解析、**ヘッダー スキーマ**フラット ファイル逆アセンブラーのデザイン時プロパティまたは**XMLNORM です。HeaderSpecName**メッセージ コンテキスト プロパティです。 いずれかの方法を使用してスキーマを指定しなかった場合、フラット ファイル逆アセンブラーは、フラット ファイル インスタンス メッセージにヘッダーが含まれないと想定します。  

## <a name="outbound-messages"></a>送信メッセージ  
 適切なスキーマを指定することで、ヘッダーを生成するために、フラット ファイル アセンブラーを構成する送信フラット ファイル インスタンス メッセージの場合、その**ヘッダー仕様名**デザイン時のプロパティまたは**XMLNORM です。HeaderSpecName**メッセージ コンテキスト プロパティです。 メッセージ コンテキスト プロパティの設定の詳細については、次を参照してください。**メッセージ コンテキスト プロパティ**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。  

## <a name="inbound-messages"></a>受信メッセージ  
 受信フラット ファイル インスタンス メッセージのヘッダーのデータは、2 つの異なる方法で保存して使用できます。 最初の方法として、フラット ファイル インスタンス メッセージのヘッダーは、対応する送信フラット ファイル インスタンス メッセージのヘッダーとして後で復元するために、メッセージ コンテキストの本文にすべて保存できます。 使用することができます、 **Preserve ヘッダー**ヘッダーを保持することを指定する受信パイプラインのプロパティです。 ヘッダーがフラット ファイル アセンブラーで指定されている場合、保存されているヘッダーが送信メッセージで使用されます。  
  
 2 つ目の方法として、対応するスキーマの 1 つ以上のフィールドのプロパティの昇格を指定して、フラット ファイル インスタンス メッセージ ヘッダーのデータの各項目をフラット ファイル メッセージ本文に関連付けられているメッセージ コンテキストにコピーできます。 プロパティの昇格の詳細については、次を参照してください。[プロパティの昇格](../core/promoting-properties.md)です。  
  
## <a name="see-also"></a>参照  
 [フラット ファイル メッセージの本文](../core/flat-file-message-bodies.md)   
 [フラット ファイル メッセージのトレーラー](../core/flat-file-message-trailers.md)   
 [フラット ファイル メッセージの構造](../core/structure-of-a-flat-file-message.md)   
 [フラット ファイル メッセージのスキーマを作成する方法](../core/how-to-create-schemas-for-flat-file-messages.md)