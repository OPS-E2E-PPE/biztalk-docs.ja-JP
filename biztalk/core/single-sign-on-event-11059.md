---
title: シングル サインオン:イベント 11059 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ac5b6ce7-8819-4b9d-85f7-f5dfaf940487
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b851e468db974456fe5f9eca00dc201fdfe1e12d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65258772"
---
# <a name="single-sign-on-event-11059"></a>シングル サインオン:イベント 11059
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                                                                       |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                               エンタープライズ シングル サインオン                                                                                                               |
| 製品バージョン |                                                                                              [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                               |
|    イベント ID     |                                                                                                                         11059                                                                                                                         |
|  イベント ソース   |                                                                                                                        ENTSSO                                                                                                                         |
|    コンポーネント    |                                                                                                                          なし                                                                                                                          |
|  シンボル名  |                                                                                                          SSO_INFO_INVALID_USER_NOT_IN_GROUP                                                                                                           |
|  メッセージ テキスト   | 指定したユーザーがアプリケーション ユーザー account.%r のメンバーではないために、マッピングを作成できませんでした。<br /><br /> Windows アカウント: %1\\% 2 %r<br /><br /> アプリケーション名: % 3 %r<br /><br /> アプリケーション ユーザー: % 4 %r<br /><br /> エラー コード: %5 |
  
## <a name="explanation"></a>説明  
 指定したユーザーがアプリケーション ユーザー アカウントのメンバーではないために、マッピングを作成できませんでした。  
  
## <a name="user-action"></a>ユーザーの操作  
 アプリケーション ユーザー アカウントのメンバーになる方法については、ENTSSO 管理者に問い合わせてください。