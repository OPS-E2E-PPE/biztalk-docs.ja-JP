---
title: 'シングル サインオン: イベント 10711 |Microsoft Docs'
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
ms.openlocfilehash: 9966cd2f588d34c3be60282bc7acfa54cd1f42b3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982579"
---
# <a name="single-sign-on-event-10711"></a>シングル サインオン: イベント 10711
## <a name="details"></a>詳細  

|                 |                                                                                                                                                                                                                                                   |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                             エンタープライズ シングル サインオン                                                                                                             |
| 製品バージョン |                                                                                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                             |
|    イベント ID     |                                                                                                                       10711                                                                                                                       |
|  イベント ソース   |                                                                                                                      ENTSSO                                                                                                                       |
|    コンポーネント    |                                                                                                                        N\A                                                                                                                        |
|  シンボル名  |                                                                                                         SSO_WARN_PS_MISSING_INITIAL_CREDS                                                                                                         |
|  メッセージ テキスト   | 外部パスワードが変更されています。 このマッピングで不足する外部資格情報フィールドの一部は既定値に設定されています。%r<br /><br /> 追跡 ID: %1 %r<br /><br /> アダプター: % 2 %r<br /><br /> アプリケーション名: % 3 %r<br /><br /> 外部アカウント: %4 |

## <a name="explanation"></a>説明  
 この警告イベントは、外部パスワード変更が受信されたが、資格情報がないことを示します。 これらのフィールドには、既定値が使用されていました。  

## <a name="user-action"></a>ユーザーの操作  
 この警告を解決するには、次の操作を行います:   

- 必要に応じて、資格情報が一致するように設定します。  

  詳細については、次のリソースを参照してください。  

- [SSO 関連アプリケーション](../core/sso-affiliate-applications.md)  

- [パスワード同期](../core/password-synchronization2.md)
