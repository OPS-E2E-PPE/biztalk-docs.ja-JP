---
title: シングル サインオン:イベント 10706 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d73db77e-5bb6-431c-a8ca-5682d7ab3d6a
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7484ddf2b669976919b493230995c4ba233b3662
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397270"
---
# <a name="single-sign-on-event-10706"></a>シングル サインオン:イベント 10706
## <a name="details"></a>詳細  

|                 |                                                                                                                           |
|-----------------|---------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                 エンタープライズ シングル サインオン                                                 |
| 製品バージョン |                                [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                 |
|    イベント ID     |                                                           10706                                                           |
|  イベント ソース   |                                                          ENTSSO                                                           |
|    コンポーネント    |                                                            該当なし                                                            |
|  シンボル名  |                                                SSO_WARN_PS_NO_GLOBAL_SYNC                                                 |
|  メッセージ テキスト   | グループ アダプターには、パスワード同期をグローバル フラグによって許可される必要があります。 グローバル flags.%r を確認してください。<br /><br /> アダプタ: %1 |

## <a name="explanation"></a>説明  
 この警告イベントは、外部パスワード同期アダプターによってパスワード同期を要求し、グローバル フラグも設定されていないことを示します。 これには、いずれかの外部システムへのパスワードの送信を許可する 2 つのフラグがあります。SSO_FLAG_FULL_SYNC_FROM_WINDOWS_TO_EXTERNAL で、もう SSO_FLAG_PARTIAL_SYNC_FROM_EXTERNAL_TO_DB の外部システムからパスワードの受信を許可します。  

## <a name="user-action"></a>ユーザーの操作  
 この警告を解決するには、次の操作を行います。  

-   SSO 管理 MMC スナップインで、(システム 使用 &#124; 文字です。プロパティと &#124; 文字です。オプション) またはコマンド ライン ツール  `ssomanage –enable winsync/extsync` グローバル フラグを有効にします。  

## <a name="more-info"></a>詳細情報

- **エンタープライズ シングル サインオン フラグ** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]

- [パスワード同期を管理する方法](../core/how-to-administer-password-synchronization.md)
