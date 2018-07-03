---
title: 'シングル サインオン: イベント 10848 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 61888420-29a6-4c64-a884-1b074b586f21
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 59a324ff0a5de2ac6d2292692f2132c10aaabc5b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991035"
---
# <a name="single-sign-on-event-10848"></a>シングル サインオン: イベント 10848
## <a name="details"></a>詳細  
  
|                 |                                                                                            |
|-----------------|--------------------------------------------------------------------------------------------|
|  製品名   |                                 エンタープライズ シングル サインオン                                  |
| 製品バージョン |                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                 |
|    イベント ID     |                                           10848                                            |
|  イベント ソース   |                                           ENTSSO                                           |
|    コンポーネント    |                                            なし                                             |
|  シンボル名  |                         ENTSSO_E_DIRECT_SYNC_NOT_ALLOWED_AMBIGUOUS                         |
|  メッセージ テキスト   | 直接パスワード同期は、そのフィールドがあいまいなため、このアプリケーションは許可されません。 |
  
## <a name="explanation"></a>説明  
 フィールドが 2 つ以上ある場合、パスワードの同期を設定できるのは 1 つだけです。  
  
## <a name="user-action"></a>ユーザーの操作  
 この状況を解決するために、アプリケーションをいったん削除し、これらのガイドラインに沿って再作成する必要があります。