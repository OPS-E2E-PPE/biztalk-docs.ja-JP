---
title: 'シングル サインオン: イベント 10662 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fe707f23-ad54-4adb-a755-8d706a75efa4
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f33d106f7c272f74f99ef537e5083d9bdb015ecb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984707"
---
# <a name="single-sign-on-event-10662"></a>シングル サインオン: イベント 10662
## <a name="details"></a>詳細  

|                 |                                                                                                                                                                                   |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                             エンタープライズ シングル サインオン                                                                             |
| 製品バージョン |                                                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                             |
|    イベント ID     |                                                                                       10662                                                                                       |
|  イベント ソース   |                                                                                      ENTSSO                                                                                       |
|    コンポーネント    |                                                                                        N\A                                                                                        |
|  シンボル名  |                                                                     SSO_INFO_WINDOWS_PASSWORD_CHANGE_RECEIVED                                                                     |
|  メッセージ テキスト   | PCNS から Windows パスワード変更を受信しました。%r<br /><br /> 追跡 ID: %1 %r<br /><br /> Windows アカウント: % 2 %r<br /><br /> 追加データ: % 3 %r<br /><br /> クライアント ユーザー: %4 |

## <a name="explanation"></a>説明  
 この情報イベントは、Windows パスワードの変更をパスワード変更通知サービスから受け取ったことを示します。  

## <a name="user-action"></a>ユーザーの操作  

-   ユーザーの操作は必要ありません。  

## <a name="more-info"></a>詳細

- [パスワード同期を管理する方法](../core/how-to-administer-password-synchronization.md)  

- **パスワード同期アダプターのプロパティ: オプション** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
