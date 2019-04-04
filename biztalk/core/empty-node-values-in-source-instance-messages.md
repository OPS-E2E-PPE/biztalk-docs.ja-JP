---
title: インスタンス メッセージのソース内の空のノードの値 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 76f9d7c8-5a82-41e9-9077-7b1ddd80a837
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8d847aace487d7b7ebd472ec96173e38315df529
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976619"
---
# <a name="empty-node-values-in-source-instance-messages"></a>送信元インスタンス メッセージの空のノードの値
マップをテストするとき、必ずしもすべてのスキーマ ノードの内容が必要になるわけではありません。  

## <a name="ceate-empty-node-values"></a>作成の空のノードの値  

1. BizTalk エディターを使用してインスタンス データを生成します。 インスタンス データ生成の詳細については、[インスタンス メッセージの生成方法](../core/how-to-generate-instance-messages.md)を参照してください。  

2. テキスト エディターで入力インスタンス メッセージを開き、空にする対象の要素と属性からデータを削除し、変更したインスタンス ファイルを保存します。  

3. スキーマの検証やテストの実行時に、変更したファイルが使用されるよう、BizTalk マッパーを構成します。 スキーマのプロパティ ウィンドウでファイルを設定します。 プロパティの設定の詳細については、**マップ ファイル プロパティ**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]を参照してください。

## <a name="see-also"></a>参照  
- [インスタンス メッセージを生成する方法](../core/how-to-generate-instance-messages.md)   
- **スキーマ プロパティのリファレンス** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
