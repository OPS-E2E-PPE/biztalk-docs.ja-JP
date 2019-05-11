---
title: エラー Messages3 |Microsoft Docs
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
ms.openlocfilehash: 789bd5cdd12d14727320e50e6c8f9bc28f721333
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65347357"
---
# <a name="error-messages"></a>エラー メッセージ
次の表では、エラー メッセージで、PeopleSoft Enterprise システムのコンポーネント インターフェイスとその説明、および考えられる修正方法を示します。  
  
 **エラー メッセージ**  
  
|エラー ID|考えられる原因/エラーの説明|考えられる修正|  
|--------------|-----------------------------------------|-------------------------|  
|E-JNI0004|Psjoa.jar がありません。<br /><br /> Java 例外が発生しました。|PeopleSoft psjoa.jar ファイルの場所を確認します。|  
|E-PSFT0030|Psjoa.jar がありません。<br /><br /> コンポーネント インターフェイス Bean のインスタンスを作成できませんでした。|PeopleSoft psjoa.jar ファイルの場所を確認します。|  
|E-PSFT0019|間違ったサーバーの名前。<br /><br /> PeopleSoft Application Server への接続に失敗しました。|PeopleSoft ホストとユーザーのパラメーターを確認します。|  
|E-PSFT0024|間違ったユーザー名とパスワード。<br /><br /> 接続に失敗しました。 エラー メッセージ:JavaClient は無効なユーザー名の場合、または誤ったパスワードを入力します。|PeopleSoft のユーザー名とパスワードに必要なし、小文字が区別されます。 適切な大文字と小文字の情報を入力することを確認します。|  
  
## <a name="see-also"></a>参照  
 [PeopleSoft のトラブルシューティング](../core/troubleshooting-peoplesoft.md)