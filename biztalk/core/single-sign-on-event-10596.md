---
title: シングル サインオン:イベント 10596 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d70aabcf-aa53-40bf-8937-44f191af1aec
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f093968363a0c67d48e8e50e4bd0d44c45d9491a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397837"
---
# <a name="single-sign-on-event-10596"></a>シングル サインオン:イベント 10596
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                                                            |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                         エンタープライズ シングル サインオン                                                                                                          |
| 製品バージョン |                                                                                         [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                         |
|    イベント ID     |                                                                                                                   10596                                                                                                                    |
|  イベント ソース   |                                                                                                                   ENTSSO                                                                                                                   |
|    コンポーネント    |                                                                                                                    なし                                                                                                                     |
|  シンボル名  |                                                                                                     SSO_WARN_TICKET_USER_NOT_IN_GROUP                                                                                                      |
|  メッセージ テキスト   | チケットの発行対象のユーザーがアプリケーション ユーザー account.%r のメンバーではないため、チケットを引き換えることはできません。<br /><br /> アプリケーション名: %1 %r<br /><br /> %2 のチケットの発行先: %r<br /><br /> アプリケーション ユーザー: %3 |
  
## <a name="explanation"></a>説明  
 チケットの発行対象のユーザーがアプリケーション ユーザー アカウントのメンバーではないため、チケットを引き換えることはできません。  
  
## <a name="user-action"></a>ユーザーの操作  
 アプリケーション ユーザー アカウントのメンバーであるユーザーにチケットを再実行します。