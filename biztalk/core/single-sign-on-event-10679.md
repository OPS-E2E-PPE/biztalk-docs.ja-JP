---
title: シングル サインオン:イベント 10679 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 645f2b74-2cbe-4c6a-b0f5-7e31f93f88c6
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1f3b551d0c5eecab6ad84b54303bd2c25bbf46eb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397438"
---
# <a name="single-sign-on-event-10679"></a>シングル サインオン:イベント 10679
## <a name="details"></a>詳細  

|                 |                                                                                                                                                                                                                                                |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                           エンタープライズ シングル サインオン                                                                                                            |
| 製品バージョン |                                                                                           [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                           |
|    イベント ID     |                                                                                                                     10679                                                                                                                      |
|  イベント ソース   |                                                                                                                     ENTSSO                                                                                                                     |
|    コンポーネント    |                                                                                                                      該当なし                                                                                                                       |
|  シンボル名  |                                                                                                          SSO_WARN_PS_MAPPING_DISABLED                                                                                                          |
|  メッセージ テキスト   | 外部パスワード変更。 マッピングは disabled.%r のため、外部アカウントのパスワードが変更されませんでした。<br /><br /> 追跡 ID: %1 %r<br /><br /> アダプター: % 2 %r<br /><br /> アプリケーション名: % 3 %r<br /><br /> 外部アカウント: %4 |

## <a name="explanation"></a>説明  
 この警告イベントは、パスワードが変更されていないこと、外部アカウントのマッピングが無効になっているため、ことを示します。  

## <a name="user-action"></a>ユーザーの操作  
 この警告は、次を解決するには。  

-   このアダプターのマッピングを有効にするのにには、SSO 管理ツールを使用します。  

## <a name="more-info"></a>詳細情報

- [パスワード同期](../core/password-synchronization2.md)  

- **パスワード同期アダプターのプロパティ:オプション** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
