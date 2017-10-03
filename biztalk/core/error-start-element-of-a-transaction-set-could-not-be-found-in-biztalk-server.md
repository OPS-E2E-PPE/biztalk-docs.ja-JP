---
title: "トランザクション セットの開始要素が見つからなかったために、トランザクション セットの処理後に発生したエラー |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d5380aee-1632-4cdf-98a1-aff87574ce4f
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 224b08046d1733aa8426909d7dddac4b10e48c8e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="error-encountered-after-processing-transaction-sets-because-the-start-element-of-a-transaction-set-could-not-be-found"></a>トランザクション セットの開始要素が見つからなかったため、トランザクション セットの処理後にエラーが発生しました
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|EDI エンジン|  
|シンボル名|InvalidEfactBiboXmlFormat|  
|メッセージ テキスト|{0} トランザクション セットを処理した後でエラーが発生しました。 トランザクション セットの開始要素が見つかりませんでした。|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、受信パイプラインが ST または UNH ヘッダーを見つけられなかったため、EDI 受信パイプラインで受信トランザクション セットを処理できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、インターチェンジの送信者に連絡し、エラーのあったトランザクション セットが ST01 または UNH1 セグメントで始まるようにしてもらいます。