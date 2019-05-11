---
title: シングル サインオン:イベント 10711 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 40722fe1-4be9-40d3-b5c5-a740a4b59f45
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a656e0bc079c2fb11a2cef59e86e914087259cef
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397242"
---
# <a name="single-sign-on-event-10711"></a>シングル サインオン:イベント 10711
## <a name="details"></a>詳細  

|                 |                                                                                                                                                                                                                                                   |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                             エンタープライズ シングル サインオン                                                                                                             |
| 製品バージョン |                                                                                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                             |
|    イベント ID     |                                                                                                                       10711                                                                                                                       |
|  イベント ソース   |                                                                                                                      ENTSSO                                                                                                                       |
|    コンポーネント    |                                                                                                                        該当なし                                                                                                                        |
|  シンボル名  |                                                                                                         SSO_WARN_PS_MISSING_INITIAL_CREDS                                                                                                         |
|  メッセージ テキスト   | 外部パスワード変更。 このマッピングのいくつか不足している外部資格情報フィールドを既定 values.%r に設定されています。<br /><br /> 追跡 ID: %1 %r<br /><br /> アダプター: % 2 %r<br /><br /> アプリケーション名: % 3 %r<br /><br /> 外部アカウント: %4 |

## <a name="explanation"></a>説明  
 この警告イベントは、資格情報がない外部パスワード変更が受信されたことを示します。 既定値は、これらのフィールドに使用されました。  

## <a name="user-action"></a>ユーザーの操作  
 この警告を解決するには、次の操作を行います。  

- 必要に応じて、一致するように資格情報を設定します。  

  詳細については、次のリソースを参照してください。  

- [SSO 関連アプリケーション](../core/sso-affiliate-applications.md)  

- [パスワード同期](../core/password-synchronization2.md)
