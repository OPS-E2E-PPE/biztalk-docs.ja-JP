---
title: シングル サインオン:イベント 10750 |Microsoft Docs
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
ms.openlocfilehash: 951a22f0b8ea5c346486d8cd2ea0882aaa2b0f05
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65307932"
---
# <a name="single-sign-on-event-10750"></a>シングル サインオン:イベント 10750
## <a name="details"></a>詳細  

|                 |                                                                                                                                                                                                                                                                  |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                                    エンタープライズ シングル サインオン                                                                                                                     |
| 製品バージョン |                                                                                                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                    |
|    イベント ID     |                                                                                                                              10750                                                                                                                               |
|  イベント ソース   |                                                                                                                              ENTSSO                                                                                                                              |
|    コンポーネント    |                                                                                                                               該当なし                                                                                                                                |
|  シンボル名  |                                                                                                                SSO_ERROR_PS_WRONG_USER_NAME_TYPE                                                                                                                 |
|  メッセージ テキスト   | PasswordChangeNotify:正しくないユーザー名の種類。 値は USER_NAME_TYPE_NT4 です。<br /><br /> アクティブな Directory.%r でターゲットが正しく構成されて<br /><br /> ユーザー名の種類: %r<br /><br /> クライアント ユーザー: % 2 %r<br /><br /> エラー コード: %3 |

## <a name="explanation"></a>説明  
 このエラー イベントは、パスワード同期は、パスワード変更通知サービス (PCNS から) のパスワード変更を受信しましたが、形式が正しくありませんが、パスワードの変更を示します。  

## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次の操作を行います。  

- PCNS の構成を確認します。 PCNS はドメイン コント ローラーでのみ実行できます。  

- Active Directory でユーザー名の種類を USER_NAME_TYPE_NT4 を構成します。  

  詳細については、次のリソースを参照してください。  

- ユーザー名の種類を指定する方法については、Active Directory のドキュメントを参照してください。  

- [パスワード同期](../core/password-synchronization2.md)
