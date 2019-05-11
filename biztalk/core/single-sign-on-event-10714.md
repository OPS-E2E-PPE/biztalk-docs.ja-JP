---
title: シングル サインオン:イベント 10714 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 59d8509f-cc3e-40fa-ba3d-3dcb0e73c67a
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 087592befd7f65241fdc413886f8245467f1e534
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397205"
---
# <a name="single-sign-on-event-10714"></a>シングル サインオン:イベント 10714
## <a name="details"></a>詳細  

|                 |                                                                                                   |
|-----------------|---------------------------------------------------------------------------------------------------|
|  製品名   |                                     エンタープライズ シングル サインオン                                     |
| 製品バージョン |                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                     |
|    イベント ID     |                                               10714                                               |
|  イベント ソース   |                                              ENTSSO                                               |
|    コンポーネント    |                                                該当なし                                                |
|  シンボル名  |                             SSO_WARN_PS_NOTIFICATION_RETRIES_EXPIRED                              |
|  メッセージ テキスト   | 再試行が期限切れ、notification.%r の破棄<br /><br /> 追跡 ID: %1 %r<br /><br /> アダプタ: %2 |

## <a name="explanation"></a>説明  
 この警告イベントは、パスワード同期通知の再試行が期限切れになり、通知が破棄されたことを示します。  

 (外部システムに Windows) からパスワードの変更は、パスワード同期アダプターに配信される、パスワード同期アダプターは、パスワードの変更が正常に処理されたことを確認します。 指定した時間内にパスワードの変更が存在しない場合、または変更時に別の問題が発生した場合は、パスワードの変更はもう一度、パスワード同期アダプターに配信されます。 これは、限られた回数 (最大試行回数) と、パスワード変更通知は破棄されます。  

## <a name="user-action"></a>ユーザーの操作  
 この警告を解決するには、次の操作を行います。  

- システムおよびアプリケーションのイベント ログで関連するイベントを確認します。  

  詳細については、次のリソースを参照してください。  

- [パスワード同期を構成する方法](../core/how-to-configure-password-synchronization.md)  

- [パスワード同期](../core/password-synchronization2.md)
