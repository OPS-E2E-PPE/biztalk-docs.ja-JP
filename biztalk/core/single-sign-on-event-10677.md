---
title: シングル サインオン:イベント 10677 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2894792b-e1c9-4c24-875d-9193cbb5cd35
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 54aeeca39a0efc16b10c7054aeafe5788c6e76af
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397453"
---
# <a name="single-sign-on-event-10677"></a>シングル サインオン:イベント 10677
## <a name="details"></a>詳細  

|                 |                                                                                                                                                                                                                                                                  |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                                    エンタープライズ シングル サインオン                                                                                                                     |
| 製品バージョン |                                                                                                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                    |
|    イベント ID     |                                                                                                                              10677                                                                                                                               |
|  イベント ソース   |                                                                                                                              ENTSSO                                                                                                                              |
|    コンポーネント    |                                                                                                                               該当なし                                                                                                                                |
|  シンボル名  |                                                                                                                  SSO_WARN_NO_EXISTING_PASSWORD                                                                                                                   |
|  メッセージ テキスト   | 外部パスワード変更。 この外部 account.%r の既存の資格情報がないために、古いパスワードを検証できません。<br /><br /> 追跡 ID: %1 %r<br /><br /> アダプター: % 2 %r<br /><br /> アプリケーション名: % 3 %r<br /><br /> 外部アカウント: %4 |

## <a name="explanation"></a>説明  
 この警告イベントは、古いパスワードに既存の資格情報があるないため、外部パスワード変更が発生することはできませんを示します。  

## <a name="user-action"></a>ユーザーの操作  
 この警告を解決するには、次の 1 つ以上の操作を行います。  

-   アダプター (イベント ログ メッセージ名) に割り当てられているどのアプリケーションを決定し、SSO 管理ツールを使用して、この外部アカウントの外部資格情報を設定します。 それらのアプリケーションのすべてでは、(特定のアカウント) の外部パスワードを設定する必要があります。  

## <a name="more-info"></a>詳細情報

- [パスワード同期](../core/password-synchronization2.md)  

- **パスワード同期アダプターのプロパティ:オプション** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
