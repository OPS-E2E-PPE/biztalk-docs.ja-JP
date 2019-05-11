---
title: シングル サインオン:イベント 10731 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 605e77f0-61f2-4a97-9ea0-bdc56344e8d9
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 630267c28a4db6b570be4c6efe73218e45f15b2f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65267518"
---
# <a name="single-sign-on-event-10731"></a>シングル サインオン:イベント 10731
## <a name="details"></a>詳細  

|                 |                                                                                                                                                                                                                                                                           |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                                         エンタープライズ シングル サインオン                                                                                                                         |
| 製品バージョン |                                                                                                        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                         |
|    イベント ID     |                                                                                                                                   10731                                                                                                                                   |
|  イベント ソース   |                                                                                                                                  ENTSSO                                                                                                                                   |
|    コンポーネント    |                                                                                                                                    該当なし                                                                                                                                    |
|  シンボル名  |                                                                                                                    SSO_WARN_INVALID_USER_NOT_IN_GROUP                                                                                                                     |
|  メッセージ テキスト   | 指定したユーザーがアプリケーション ユーザー account.%r のメンバーではないために、マッピングを作成できませんでした。<br /><br /> ドメイン名: %1 %r<br /><br /> ユーザー名: % 2 %r<br /><br /> アプリケーション名: % 3 %r<br /><br /> アプリケーション ユーザー: % 4 %r<br /><br /> エラー コード: %5 |

## <a name="explanation"></a>説明  
 この警告イベントは、指定したユーザーがアプリケーション ユーザー アカウントのメンバーではないためは、マッピングを作成できませんでしたを示します。  

 関連アプリケーションごとに、アプリケーション ユーザーのグループのアカウントが存在します。 このアカウントのメンバーでは、関連アプリケーションで資格情報を確認することができ、関連アプリケーションで資格情報マッピングを管理できます。  

## <a name="user-action"></a>ユーザーの操作  
 この警告を解決するには、次の操作を行います。  

- 指定された関連アプリケーションのアプリケーション ユーザーのグループに指定されたユーザーを追加します。  

  詳細については、次のリソースを参照してください。  

- [SSO ユーザー グループ](../core/sso-user-groups.md)  

- [SSO 関連アプリケーション](../core/sso-affiliate-applications.md)
