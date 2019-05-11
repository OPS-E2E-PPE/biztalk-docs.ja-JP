---
title: シングル サインオン:イベント 11071 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9c0f61b9-cd86-482b-a8fe-0093a928c89b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 43105808e83b06f780736e7168581d3854305439
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65247485"
---
# <a name="single-sign-on-event-11071"></a>シングル サインオン:イベント 11071
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                               |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                   エンタープライズ シングル サインオン                                                                                   |
| 製品バージョン |                                                                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                   |
|    イベント ID     |                                                                                             11071                                                                                             |
|  イベント ソース   |                                                                                            ENTSSO                                                                                             |
|    コンポーネント    |                                                                                              なし                                                                                              |
|  シンボル名  |                                                                         SSO_WARN_PS_WIN_CHANGE_DISCARDED_ZERO_LENGTH                                                                          |
|  メッセージ テキスト   | Windows パスワードの長さがゼロ characters.%r ために、Windows パスワードの変更は破棄されました。<br /><br /> 追跡 ID: %1 %r<br /><br /> Windows アカウント: % 2 %r<br /><br /> クライアント ユーザー: %3 |
  
## <a name="explanation"></a>説明  
 Windows パスワードの長さがゼロの文字であるために、Windows パスワードの変更は破棄されました。 Windows アカウントとクライアントのユーザー名が提供されます。  
  
## <a name="user-action"></a>ユーザーの操作  
 SSO システムで必要な文字の種類と数を使用して、もう一度パスワードを変更します。