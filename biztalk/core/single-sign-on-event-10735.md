---
title: シングル サインオン:イベント 10735 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 31c791c6-1901-4441-b329-ed75833cb83e
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f3e7752733a437f3526af7d5ac2790d2ffac64fc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291779"
---
# <a name="single-sign-on-event-10735"></a>シングル サインオン:イベント 10735
## <a name="details"></a>詳細  

|                 |                                                                                                                                                                                                                                                    |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                             エンタープライズ シングル サインオン                                                                                                              |
| 製品バージョン |                                                                                             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                             |
|    イベント ID     |                                                                                                                       10735                                                                                                                        |
|  イベント ソース   |                                                                                                                       ENTSSO                                                                                                                       |
|    コンポーネント    |                                                                                                                        該当なし                                                                                                                         |
|  シンボル名  |                                                                                                              SSO_WARN_PS_APP_DISABLED                                                                                                              |
|  メッセージ テキスト   | 外部パスワード変更。 アプリケーションが disabled.%r であるため、外部アカウントのパスワードが変更されませんでした。<br /><br /> 追跡 ID: %1 %r<br /><br /> アダプター: % 2 %r<br /><br /> アプリケーション名: % 3 %r<br /><br /> 外部アカウント: %4 |

## <a name="explanation"></a>説明  
 この警告イベントでは、パスワードが変更されていないこと、外部アカウントのため、アプリケーションが無効になっていることを示します。  

## <a name="user-action"></a>ユーザーの操作  
 この警告を解決するには、次の操作を行います。  

- 関連アプリケーションを有効にします。  

  詳細については、次のリソースを参照してください。  

- [関連アプリケーションを有効にする方法](../core/how-to-enable-an-affiliate-application.md)  

- [パスワード同期](../core/password-synchronization2.md)
