---
title: シングル サインオン:イベント 11035 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d551083c-a897-4a76-a40c-2254d3a3e52e
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 39b07359061b7e855e8ea53abee64ef567668395
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395249"
---
# <a name="single-sign-on-event-11035"></a>シングル サインオン:イベント 11035
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                                                                                                                                        |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                                                               エンタープライズ シングル サインオン                                                                                                                                                |
| 製品バージョン |                                                                                                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                               |
|    イベント ID     |                                                                                                                                                         11035                                                                                                                                                          |
|  イベント ソース   |                                                                                                                                                         ENTSSO                                                                                                                                                         |
|    コンポーネント    |                                                                                                                                                          なし                                                                                                                                                           |
|  シンボル名  |                                                                                                                                           SSO_INFO_PS_WIN_CHANGE_NO_ADAPTER                                                                                                                                            |
|  メッセージ テキスト   | Windows パスワードが変更されています。 この Windows アカウントに対するマッピングが検出されましたが、このアプリケーションに対してはパスワード同期が構成されていないため無視されました。%r<br /><br /> 追跡 ID: %1 %r<br /><br /> Windows アカウント: % 2 %r<br /><br /> アプリケーションの場合: % 3 %r<br /><br /> 外部アカウント: % 4 %r<br /><br /> クライアント ユーザー: %5 |
  
## <a name="explanation"></a>説明  
 この Windows アカウントに対するマッピングが検出されましたが、このアプリケーションに対してはパスワード同期が構成されていないため無視されました。  
  
## <a name="user-action"></a>ユーザーの操作  
 パスワード同期の構成方法の詳細については、次を参照してください。[パスワード同期](../core/password-synchronization2.md)します。