---
title: シングル サインオン:イベント 10707 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 59629786-4f98-4861-aba3-153670bafc12
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e323f9b712e566278bf43224611b2d39e74dcecb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397281"
---
# <a name="single-sign-on-event-10707"></a>シングル サインオン:イベント 10707
## <a name="details"></a>詳細  

|                 |                                                                                                                                                                        |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                       エンタープライズ シングル サインオン                                                                        |
| 製品バージョン |                                                       [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                       |
|    イベント ID     |                                                                                 10707                                                                                  |
|  イベント ソース   |                                                                                 ENTSSO                                                                                 |
|    コンポーネント    |                                                                                  該当なし                                                                                   |
|  シンボル名  |                                                                        SSO_WARN_PS_NO_APP_SYNC                                                                         |
|  メッセージ テキスト   | このアダプターのパスワード同期フラグは、パスワード同期を許可する必要があり、グローバル フラグに一致する必要があります。 アダプタ フラグおよびグローバル flags.%r を確認してください。<br /><br /> アダプタ: %1 |

## <a name="explanation"></a>説明  
 この警告イベントは、このアダプターのパスワード同期フラグがパスワード同期を許可する必要がありますする必要がありますには、グローバル フラグと一致することを示します。  

 パスワード同期アダプターのパスワード同期は、2 つのフラグによって制御されますが、1 つの送信を許可 (SSO_FLAG_FULL_SYNC_FROM_WINDOWS_TO_EXTERNAL) の外部システムにパスワードと別の外部システム (SSO_FLAG_PARTIAL_ からパスワードの受信を許可します。SYNC_FROM_EXTERNAL_TO_DB)。 正常にパスワード同期これら両方の「グローバル フラグ」と特定のアダプター フラグも設定する必要があります。 この警告イベントは、外部パスワード同期アダプターによってパスワード同期が要求され、「グローバル フラグ」とアダプター フラグの両方のこれらのフラグも設定されているときに発行されます。  

## <a name="user-action"></a>ユーザーの操作  
 この警告を解決するには、次の操作を行います。  

-   SSO 管理 MMC スナップインを使用して (システム &#124; 文字です。プロパティと &#124; 文字です。オプション) またはコマンド ライン ツール  `ssomanage –enable winsync/extsync` グローバル フラグを有効にします。  

## <a name="more-info"></a>詳細情報

- **エンタープライズ シングル サインオン フラグ** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]  

- [パスワード同期を管理する方法](../core/how-to-administer-password-synchronization.md)
