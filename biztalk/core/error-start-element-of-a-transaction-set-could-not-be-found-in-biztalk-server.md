---
title: トランザクション セットの開始要素が見つからなかったため、トランザクション セットの処理後に発生したエラー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d5380aee-1632-4cdf-98a1-aff87574ce4f
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 74ea9b059ed75d88a8f48287d553e670d2c7d755
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984483"
---
# <a name="error-encountered-after-processing-transaction-sets-because-the-start-element-of-a-transaction-set-could-not-be-found"></a>トランザクション セットの開始要素が見つからなかったため、トランザクション セットの処理後にエラーが発生しました
## <a name="details"></a>詳細  
  
|                 |                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------|
|  製品名   |                [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                 |
| 製品バージョン |                            [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                             |
|    イベント ID     |                                                         -                                                         |
|  イベント ソース   |              [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI               |
|    コンポーネント    |                                                    EDI エンジン                                                     |
|  シンボル名  |                                             InvalidEfactBiboXmlFormat                                             |
|  メッセージ テキスト   | 処理後に発生したエラー{0}トランザクション セットします。 トランザクション セットの開始要素が見つかりませんでした。 |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、受信パイプラインが ST または UNH ヘッダーを見つけられなかったため、EDI 受信パイプラインで受信トランザクション セットを処理できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、インターチェンジの送信者に連絡し、エラーのあったトランザクション セットが ST01 または UNH1 セグメントで始まるようにしてもらいます。