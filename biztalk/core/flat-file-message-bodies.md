---
title: フラット ファイル メッセージの本文 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 097e49a1-75d2-44a4-9372-d78de7b7597c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0ef973fca636f4e75f05e26638a841e9e51d39b3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387950"
---
# <a name="flat-file-message-bodies"></a>フラット ファイル メッセージの本文
フラット ファイル インスタンス メッセージの本文は必須では、フラット ファイル逆アセンブラーの処理を 1 つまたは複数の XML インスタンス メッセージにです。 受信フラット ファイル インスタンス メッセージの本文に含まれるデータを把握するには、本文に対応するフラット ファイル スキーマのフラット ファイル逆アセンブラーを構成する必要があります。 使用して、スキーマを指定することができます、**ドキュメント スキーマ**フラット ファイル逆アセンブラーのデザイン時プロパティまたは**XMLNORM します。DocumentSpecName**メッセージ コンテキスト プロパティ。 フラット ファイル インスタンス メッセージにはボディ部を設定する必要がありますので、これら 2 つのメソッドのいずれかを使用して、適切なスキーマを構成する必要があります。  
  
 送信フラット ファイル インスタンス メッセージの場合、フラット ファイル アセンブラーは、インスタンス メッセージの本文の適切なフラット ファイル スキーマを動的に決定することができます。 フラット ファイル アセンブラーは、送信メッセージの XML バージョンに存在する必要があります、ルート要素の名前とターゲットの名前空間の組み合わせは、メッセージの種類から適切なスキーマを決定します。 構成して使用するフラット ファイル スキーマを明示的に構成する代わりに、**ドキュメント スキーマ**フラット ファイル アセンブラーのデザイン時プロパティまたは**XMLNORM します。DocumentSpecName**メッセージ コンテキスト プロパティ。  
  
 受信フラット ファイル インスタンス メッセージの本文内のデータは、受信インスタンス メッセージを処理するフラット ファイル逆アセンブラーが使用するフラット ファイル スキーマのプロパティの昇格を指定することで、対応するメッセージ コンテキストにコピーできます。 同様に、送信メッセージを処理するフラット ファイル アセンブラーが使用するフラット ファイル スキーマのプロパティの降格を指定することで、送信フラット ファイル インスタンス メッセージにメッセージ コンテキスト内のデータをコピーできます。  
  
## <a name="see-also"></a>参照  
 [フラット ファイル メッセージのヘッダー](../core/flat-file-message-headers.md)   
 [フラット ファイル メッセージのトレーラー](../core/flat-file-message-trailers.md)   
 [フラット ファイル メッセージの構造](../core/structure-of-a-flat-file-message.md)   
 [フラット ファイル メッセージのスキーマを作成する方法](../core/how-to-create-schemas-for-flat-file-messages.md)