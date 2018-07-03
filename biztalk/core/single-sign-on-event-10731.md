---
title: 'シングル サインオン: イベント 10731 |Microsoft Docs'
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
ms.openlocfilehash: d51174c0a7241f7f8bb8b5287cb03b139d6f87c0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998515"
---
# <a name="single-sign-on-event-10731"></a>シングル サインオン: イベント 10731
## <a name="details"></a>詳細  

|                 |                                                                                                                                                                                                                                                                           |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                                         エンタープライズ シングル サインオン                                                                                                                         |
| 製品バージョン |                                                                                                        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                         |
|    イベント ID     |                                                                                                                                   10731                                                                                                                                   |
|  イベント ソース   |                                                                                                                                  ENTSSO                                                                                                                                   |
|    コンポーネント    |                                                                                                                                    N\A                                                                                                                                    |
|  シンボル名  |                                                                                                                    SSO_WARN_INVALID_USER_NOT_IN_GROUP                                                                                                                     |
|  メッセージ テキスト   | 指定されたユーザーが Application Users アカウントのメンバーではないため、マッピングを作成できませんでした。%r<br /><br /> ドメイン名: %1 %r<br /><br /> ユーザー名: % 2 %r<br /><br /> アプリケーション名: % 3 %r<br /><br /> アプリケーション ユーザー: % 4 %r<br /><br /> エラー コード: %5 |

## <a name="explanation"></a>説明  
 この警告イベントは、指定されたユーザーがアプリケーション ユーザー アカウントのメンバーではないために、マッピングを作成できなかったことを示します。  

 アプリケーション ユーザーのグループ アカウントは、関連アプリケーションごとに存在します。 このアカウントのメンバーは、関連アプリケーションで資格情報を検証でき、関連アプリケーションで資格情報のマッピングを管理できます。  

## <a name="user-action"></a>ユーザーの操作  
 この警告を解決するには、次の操作を行います:   

- 指定したユーザーを、指定した関連アプリケーションのアプリケーション ユーザーのグループに追加します。  

  詳細については、次のリソースを参照してください。  

- [SSO ユーザー グループ](../core/sso-user-groups.md)  

- [SSO 関連アプリケーション](../core/sso-affiliate-applications.md)
