---
title: エラー Messages3 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- error messages
ms.assetid: 10ea12bb-eacb-477a-bc88-28f999e60a02
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f1b9dd41280593de1472cd6af57ae8d1eb9fc58
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241778"
---
# <a name="error-messages"></a>エラー メッセージ
次の表は、PeopleSoft Enterprise システムのコンポーネント インターフェイスのエラー メッセージ、各メッセージの説明、および考えられる修正方法を示しています。  
  
 **エラー メッセージ**  
  
|エラー ID|考えられる原因/エラーの説明|考えられる修正|  
|--------------|-----------------------------------------|-------------------------|  
|E-JNI0004|psjoa.jar がありません。<br /><br /> Java 例外が発生しました。|PeopleSoft psjoa.jar ファイルの場所を確認してください。|  
|E-PSFT0030|psjoa.jar がありません。<br /><br /> コンポーネント インターフェイス Bean のインスタンスを作成できませんでした。|PeopleSoft psjoa.jar ファイルの場所を確認してください。|  
|E-PSFT0019|サーバー名が正しくありません。<br /><br /> PeopleSoft Application Server への接続に失敗しました。|PeopleSoft ホスト パラメーターとユーザー パラメーターを確認してください。|  
|E-PSFT0024|ユーザー名とパスワードが正しくありません。<br /><br /> 接続に失敗しました。 エラー メッセージ: は JavaClient は無効なユーザー名、または誤ったパスワードを入力します。|PeopleSoft のユーザー名とパスワードは必須であり、大文字と小文字が区別されます。 入力した情報の大文字と小文字の区別が正しいことを確認してください。|  
  
## <a name="see-also"></a>参照  
 [PeopleSoft のトラブルシューティング](../core/troubleshooting-peoplesoft.md)