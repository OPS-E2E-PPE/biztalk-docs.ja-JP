---
title: 'シングル サインオン: イベント 10592 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e044f9bd-c384-4f08-81f0-699e0c774c45
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f03f32a956cabe906c22afe0c89a096a1ad213f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270442"
---
# <a name="single-sign-on-event-10592"></a>シングル サインオン: イベント 10592
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10592|  
|イベント ソース|ENTSSO|  
|コンポーネント|なし|  
|シンボル名|SSO_WARN_TICKET_DECRYPT_FAILED|  
|メッセージ テキスト|チケットを暗号化解除できませんでした。 チケットが有効ではないか、期限切れの可能性があります。%r<br /><br /> アプリケーション名: %1 %r<br /><br /> エラー コード: %2|  
  
## <a name="explanation"></a>説明  
 チケットが有効ではないか、期限切れの可能性があります。  
  
## <a name="user-action"></a>ユーザーの操作  
 使用するチケットが有効で、期限が切れていないことを確認します。