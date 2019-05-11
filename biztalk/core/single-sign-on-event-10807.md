---
title: シングル サインオン:イベント 10807 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 882c01c6-70db-4986-9f4b-f08335424250
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 774769a952436729e3a32c5aeaf9d3d8eb98243c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65267527"
---
# <a name="single-sign-on-event-10807"></a>シングル サインオン:イベント 10807
## <a name="details"></a>詳細  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  製品名   |                 エンタープライズ シングル サインオン                  |
| 製品バージョン | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    イベント ID     |                           10807                            |
|  イベント ソース   |                           ENTSSO                           |
|    コンポーネント    |                            なし                             |
|  シンボル名  |        ENTSSO_E_TOO_MANY_UNCONFIRMED_NOTIFICATIONS         |
|  メッセージ テキスト   |            未確認の通知が多すぎます。             |
  
## <a name="explanation"></a>説明  
 たびに、パスワード変更通知が送信される、確認メッセージを受信します。 この場合、確認なしの通知の制限を超過しました。  
  
## <a name="user-action"></a>ユーザーの操作  
 パスワード同期アダプターを確認します。