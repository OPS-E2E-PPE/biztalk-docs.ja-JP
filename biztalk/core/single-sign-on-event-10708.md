---
title: シングル サインオン:イベント 10708 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 63675191-41cb-43fc-9355-e4ddc3f354c5
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 24de44e04ecbbd5aca453a1c45a588bd4d5b63b3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397260"
---
# <a name="single-sign-on-event-10708"></a>シングル サインオン:イベント 10708
## <a name="details"></a>詳細  

|                 |                                                                                                                                |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                   エンタープライズ シングル サインオン                                                    |
| 製品バージョン |                                   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                   |
|    イベント ID     |                                                             10708                                                              |
|  イベント ソース   |                                                             ENTSSO                                                             |
|    コンポーネント    |                                                              該当なし                                                               |
|  シンボル名  |                                                    SSO_WARN_PS_NO_WIN_SYNC                                                     |
|  メッセージ テキスト   | Windows からのパスワード同期が許可されていません。 グローバル flags.%r を確認してください。<br /><br /> 追跡 ID: %1 %r<br /><br /> クライアント ユーザー: %2 |

## <a name="explanation"></a>説明  
 この警告イベントは、Windows によってパスワード同期が要求し、グローバル フラグも設定されていないことを示します。 これには、いずれかの外部システムへのパスワードの送信を許可する 2 つのフラグがあります。SSO_FLAG_FULL_SYNC_FROM_WINDOWS_TO_EXTERNAL で、もう SSO_FLAG_PARTIAL_SYNC_FROM_EXTERNAL_TO_DB の外部システムからパスワードの受信を許可します。  

## <a name="user-action"></a>ユーザーの操作  
 この警告を解決するには、次の操作を行います。  

-   SSO 管理 MMC スナップインで、(システム 使用 &#124; 文字です。プロパティと &#124; 文字です。オプション) またはコマンド ライン ツール  `ssomanage –enable winsync/extsync` グローバル フラグを有効にします。  

## <a name="more-info"></a>詳細情報

- **エンタープライズ シングル サインオン フラグ** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]

- [パスワード同期を管理する方法](../core/how-to-administer-password-synchronization.md)
