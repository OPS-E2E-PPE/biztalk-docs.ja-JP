---
title: 'シングル サインオン: イベント 10817 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f1668b81-e7f4-46d2-aebe-47007f70372b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e42873f0b56c43a7c997a2476ba2b15148d4639
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979195"
---
# <a name="single-sign-on-event-10817"></a>シングル サインオン: イベント 10817
## <a name="details"></a>詳細  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  製品名   |                 エンタープライズ シングル サインオン                  |
| 製品バージョン | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    イベント ID     |                           10817                            |
|  イベント ソース   |                           ENTSSO                           |
|    コンポーネント    |                            なし                             |
|  シンボル名  |              ENTSSO_E_NOTIFICATION_NOT_FOUND               |
|  メッセージ テキスト   |         指定された通知が見つかりませんでした。          |
  
## <a name="explanation"></a>説明  
 パスワード変更で指定された通知の GUID が見つかりません。  
  
## <a name="user-action"></a>ユーザーの操作  
 このパスワード同期アダプターの構成を調べて、通知の正しい GUID を確認します。