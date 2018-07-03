---
title: 'シングル サインオン: イベント 10678 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6af92ce1-fdac-432f-be6b-cf8958aee776
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1fa3cde1cb26023ab4115f5538b8a3081eaaf1bc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977435"
---
# <a name="single-sign-on-event-10678"></a>シングル サインオン: イベント 10678
## <a name="details"></a>詳細  

|                 |                                                                                                                                                                                                                                                                 |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                                    エンタープライズ シングル サインオン                                                                                                                    |
| 製品バージョン |                                                                                                   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                    |
|    イベント ID     |                                                                                                                              10678                                                                                                                              |
|  イベント ソース   |                                                                                                                             ENTSSO                                                                                                                              |
|    コンポーネント    |                                                                                                                               N\A                                                                                                                               |
|  シンボル名  |                                                                                                                   SSO_WARN_PASSWORD_MISMATCH                                                                                                                    |
|  メッセージ テキスト   | 外部パスワードが変更されています。 アダプターによって指定された古いパスワードは、外部アカウントの既存のパスワードと一致しません。%r<br /><br /> 追跡 ID: %1 %r<br /><br /> アダプター: % 2 %r<br /><br /> アプリケーション名: % 3 %r<br /><br /> 外部アカウント: %4 |

## <a name="explanation"></a>説明  
 この警告イベントは、アダプターによって指定された古いパスワードが、外部アカウントの既存のパスワードと一致しないことを示します。  

## <a name="user-action"></a>ユーザーの操作  
 この警告を解消するには、次の手順を実行します。  

-   このアダプターにどのアプリケーションが割り当てられていたかを確認し (イベント ログ メッセージに名前があります)、SSO 管理ツールを使用してこの外部アカウントの外部資格情報を設定します。 それらのアプリケーションのすべてに対して (指定されたアカウントに) 外部パスワードを設定する必要があります。  

## <a name="more-info"></a>詳細

- [パスワード同期](../core/password-synchronization2.md)  

- **パスワード同期アダプターのプロパティ: オプション** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
