---
title: シングル サインオン:イベント 10661 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c3418f37-770d-4021-9341-5dbe99689da6
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e7aa13b06dfcf0d57c90271cd924b804717ca2f2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397580"
---
# <a name="single-sign-on-event-10661"></a>シングル サインオン:イベント 10661
## <a name="details"></a>詳細  

|                 |                                                                                     |
|-----------------|-------------------------------------------------------------------------------------|
|  製品名   |                              エンタープライズ シングル サインオン                              |
| 製品バージョン |             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]              |
|    イベント ID     |                                        10661                                        |
|  イベント ソース   |                                       ENTSSO                                        |
|    コンポーネント    |                                         該当なし                                         |
|  シンボル名  |                    SSO_ERROR_PASSWORD_SYNC_WINDOWS_START_FAILED                     |
|  メッセージ テキスト   | Start.%r (PCNS から) Windows のパスワード同期が失敗しました<br /><br /> エラー コード: %1 |

## <a name="explanation"></a>説明  
 このエラー イベントでは、Windows のパスワード同期を開始できなかったことを示します。  

## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、以下の 1 つ以上の操作を実行します。  

-   アプリケーションとシステムのイベント ログで関連するイベントを確認します。  

-   アダプター構成プロパティを確認します。  

## <a name="more-info"></a>詳細情報

- [パスワード同期を管理する方法](../core/how-to-administer-password-synchronization.md)  

- **エンタープライズ シングル サインオン UI のヘルプ** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
