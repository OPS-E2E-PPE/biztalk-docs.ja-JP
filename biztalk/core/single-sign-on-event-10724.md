---
title: シングル サインオン:イベント 10724 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 022a6f73-a24b-4058-91a5-b831f6875409
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e5494af19164c6c2621196ccd481d8510be58794
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65303313"
---
# <a name="single-sign-on-event-10724"></a>シングル サインオン:イベント 10724
## <a name="details"></a>詳細  

|                 |                                                                                                                                                                                                    |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                     エンタープライズ シングル サインオン                                                                                      |
| 製品バージョン |                                                                     [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                     |
|    イベント ID     |                                                                                               10724                                                                                                |
|  イベント ソース   |                                                                                               ENTSSO                                                                                               |
|    コンポーネント    |                                                                                                該当なし                                                                                                 |
|  シンボル名  |                                                                                    SSO_ERROR_REPLAY_SECURITY_2                                                                                     |
|  メッセージ テキスト   | 再生または進行ファイルでのセキュリティが元の value.%r から変更されました<br /><br /> ファイル名: %1 %r<br /><br /> 現在のファイルのセキュリティ: % 2 %r<br /><br /> 元のファイルのセキュリティ: %3 |

## <a name="explanation"></a>説明  
 このエラー イベントは、または進行ファイルでのセキュリティが変更されたことを示します。  

 再生ファイルは、再生ファイルのディレクトリに格納されます。 既定では、SSO サービス アカウントを使用して、再生ファイルと再生ファイルのディレクトリの両方を作成します。 SSO は、変更が行われていないことを再生ファイルと再生ファイル ディレクトリのセキュリティ構成が作成後かを確認します。 再生ファイルのディレクトリは、別のアカウントで作成されている場合、パスワード同期がそのディレクトリ内で再生ファイルを作成しようとしたときにこのエラーが返されますことができます。 ユーザーが再生ファイルと再生ファイル ディレクトリのセキュリティ構成を変更されないことを強くお勧めします。  

## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次の操作を行います。  

- 再生ファイルの作成に使用するアカウントのアクセス許可を確認します。 これは、通常、SSO システム アカウントです。  

  詳細については、次のリソースを参照してください。  

- [パスワード同期を構成する方法](../core/how-to-configure-password-synchronization.md)  

- [パスワード同期](../core/password-synchronization2.md)
