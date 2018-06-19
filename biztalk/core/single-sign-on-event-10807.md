---
title: 'シングル サインオン: イベント 10807 |Microsoft ドキュメント'
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
ms.openlocfilehash: 4e269b22bc8ea2fec013123d515ac04bd3f60d46
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277698"
---
# <a name="single-sign-on-event-10807"></a>シングル サインオン: イベント 10807
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10807|  
|イベント ソース|ENTSSO|  
|コンポーネント|なし|  
|シンボル名|ENTSSO_E_TOO_MANY_UNCONFIRMED_NOTIFICATIONS|  
|メッセージ テキスト|未確認の通知が多すぎます。|  
  
## <a name="explanation"></a>説明  
 パスワード変更通知が送信されるたびに、確認メッセージが受信されます。 この場合、確認されていない通知の制限値を超えています。  
  
## <a name="user-action"></a>ユーザーの操作  
 パスワード同期アダプターを確認します。