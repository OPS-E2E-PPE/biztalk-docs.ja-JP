---
title: シングル サインオン:イベント 11034 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 828bc5fb-12ab-4eea-94f2-2434ad0ee033
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 87f8b49a2834199cd3f206afedd22c2542422725
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401036"
---
# <a name="single-sign-on-event-11034"></a>シングル サインオン:イベント 11034
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                                                                                                                                                                                                         |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                                                                                                エンタープライズ シングル サインオン                                                                                                                                                                                |
| 製品バージョン |                                                                                                                                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                                                |
|    イベント ID     |                                                                                                                                                                                          11034                                                                                                                                                                                          |
|  イベント ソース   |                                                                                                                                                                                         ENTSSO                                                                                                                                                                                          |
|    コンポーネント    |                                                                                                                                                                                           なし                                                                                                                                                                                           |
|  シンボル名  |                                                                                                                                                                        SSO_INFO_PS_WIN_CHANGE_APP_INCORRECT_TYPE                                                                                                                                                                        |
|  メッセージ テキスト   | Windows パスワードが変更されています。 この Windows アカウントのマッピングが検出されましたが、アプリケーションが適切な種類ではないために無視されました。 Windows パスワード同期をサポートしているアプリケーションの種類は 'Individual' または 'Group' だけです。%r<br /><br /> 追跡 ID: %1 %r<br /><br /> Windows アカウント: % 2 %r<br /><br /> アプリケーションの場合: % 3 %r<br /><br /> 外部アカウント: % 4 %r<br /><br /> クライアント ユーザー: %5 |
  
## <a name="explanation"></a>説明  
 Windows パスワード同期をサポートしているアプリケーションの種類は 'Individual' または 'Group' だけです。  
  
## <a name="user-action"></a>ユーザーの操作  
 詳細については、次を参照してください。[パスワード同期](../core/password-synchronization2.md)します。