---
title: シングル サインオン:イベント 11033 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eed8e984-2b6c-4a9e-8603-175fdcabeb0a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da9c77a8d8ea41a12e8b122dc21e4f0b8d3adce0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65303407"
---
# <a name="single-sign-on-event-11033"></a>シングル サインオン:イベント 11033
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                                                                                                               |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                                                   エンタープライズ シングル サインオン                                                                                                                                   |
| 製品バージョン |                                                                                                                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                   |
|    イベント ID     |                                                                                                                                             11033                                                                                                                                             |
|  イベント ソース   |                                                                                                                                            ENTSSO                                                                                                                                             |
|    コンポーネント    |                                                                                                                                              なし                                                                                                                                              |
|  シンボル名  |                                                                                                                              SSO_INFO_PS_WIN_CHANGE_APP_DISABLED                                                                                                                              |
|  メッセージ テキスト   | Windows パスワードが変更されています。 この Windows アカウントのマッピングが検出されましたので、アプリケーションが disabled.%r は無視されます。<br /><br /> 追跡 ID: %1 %r<br /><br /> Windows アカウント: % 2 %r<br /><br /> アプリケーションの場合: % 3 %r<br /><br /> 外部アカウント: % 4 %r<br /><br /> クライアント ユーザー: %5 |
  
## <a name="explanation"></a>説明  
 この Windows アカウントのマッピングが検出されましたが、アプリケーションが無効になっているため、無視されます。  
  
## <a name="user-action"></a>ユーザーの操作  
 アプリケーションを有効にするのを参照してください。[関連アプリケーションを有効にする方法](../core/how-to-enable-an-affiliate-application.md)します。