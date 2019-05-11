---
title: TestCrypto |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, TestCrypto utility
- troubleshooting, TestCrypto utility
- TestCrypto utility
ms.assetid: 02768794-64ac-4d99-930c-738bed9626c5
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 881cd9ee8729a18f5829490e42c0795aa1267e43
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65280516"
---
# <a name="testcrypto"></a>TestCrypto
TestCrypto ユーティリティを使用して、メッセージの暗号化解除エラーのトラブルシューティングします。 このユーティリティは、復号化が失敗したかどうかを示します。 ユーティリティには、証明書を通知し、表示することを示します、復号化が成功すると、復号化されたメッセージ。  
  
 TestCrypto を実行するには、暗号化されていないヘッダー メッセージの暗号化された部分だけを含むファイルにします。 受信メッセージをスニッフィングするかからのメッセージを取得することによって、テキスト ファイルにメッセージから暗号化されたバイナリ ラージ オブジェクト (BLOB) を抽出`MessageStorageIn`します。  
  
 メッセージの取得の詳細については`MessageStorageIn`を参照してください[GetMessages サンプル](../../adapters-and-accelerators/accelerator-rosettanet/getmessages-sample.md)します。  
  
## <a name="location-in-sdk"></a>SDK でのパス  
 \<*drive*\>\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK  
  
## <a name="running-testcrypto"></a>TestCrypto の実行  
  
#### <a name="to-run-testcrypto"></a>TestCrypto を実行するには  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**アクセサリ**、順にクリックします**コマンド プロンプト**します。  
  
2.  移動\<*ドライブ*\>\Program Files (x86) \Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk します。  
  
3.  コマンド プロンプトで「 **TestCrypto.exe \<filename\>** し、ENTER キーを押します。  
  
## <a name="remarks"></a>コメント  
 復号化は、ユーティリティが検出される証明書が必要な有効な証明書ではない場合、または証明書が見つからない場合に失敗します。  
  
## <a name="see-also"></a>参照  
 [ユーティリティ](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md)
