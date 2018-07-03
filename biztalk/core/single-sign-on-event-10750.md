---
title: 'シングル サインオン: イベント 10750 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2a0fdaf2-d429-40b9-adc3-eb134687fb1a
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 28526c6695cbf8f9c29e99621d6cb2f852fa7021
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984371"
---
# <a name="single-sign-on-event-10750"></a>シングル サインオン: イベント 10750
## <a name="details"></a>詳細  

|                 |                                                                                                                                                                                                                                                                  |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                                    エンタープライズ シングル サインオン                                                                                                                     |
| 製品バージョン |                                                                                                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                    |
|    イベント ID     |                                                                                                                              10750                                                                                                                               |
|  イベント ソース   |                                                                                                                              ENTSSO                                                                                                                              |
|    コンポーネント    |                                                                                                                               N\A                                                                                                                                |
|  シンボル名  |                                                                                                                SSO_ERROR_PS_WRONG_USER_NAME_TYPE                                                                                                                 |
|  メッセージ テキスト   | PasswordChangeNotify: 正しくないユーザー名の種類。 指定できる値は USER_NAME_TYPE_NT4 のみです。<br /><br /> ターゲットが Active Directory で正しく構成されていません。%r<br /><br /> ユーザー名の種類: %r<br /><br /> クライアント ユーザー: % 2 %r<br /><br /> エラー コード: %3 |

## <a name="explanation"></a>説明  
 このエラー イベントは、パスワード同期が、パスワード変更通知サービス (PCNS) からパスワード変更を受け取ったが、パスワード変更の形式が正しくなかったことを示します。  

## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次の操作を行います。  

- PCNS の構成を確認します。 PCNS はドメイン コントローラーでのみ実行できます。  

- Active Directory で、ユーザー名の種類を USER_NAME_TYPE_NT4 に構成します。  

  詳細については、次のリソースを参照してください。  

- ユーザー名の種類を指定する方法については、Active Directory のドキュメントを参照してください。  

- [パスワード同期](../core/password-synchronization2.md)
