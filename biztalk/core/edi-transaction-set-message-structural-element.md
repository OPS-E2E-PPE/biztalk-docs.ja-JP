---
title: EDI トランザクション セット メッセージの構造体要素 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: caea8408-c09c-4525-a9c9-18abe4432594
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d49288e9a311c9766e61fe985b9e279a8660f4ef
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239186"
---
# <a name="edi-transaction-set-message-structural-element"></a>EDI トランザクション セット メッセージの構造体要素
トランザクション セット (X12 エンコード) またはメッセージ (EDIFACT エンコード) には、メッセージ データを構成するセグメントが含まれています。 トランザクション セットは、ヘッダー、データ セグメントのコレクション、およびトレーラで構成されています。 トランザクションの処理に必要なすべての詳細情報は、トランザクション セット内で使用できます。  
  
 トランザクション セットは、ST トランザクション セット ヘッダー (X12 の場合) または UNH メッセージ ヘッダー (EDIFACT の場合) で開始する必要があります。 また、SE トランザクション セット トレーラ (X12 の場合) または UNT メッセージ トレーラ (EDIFACT の場合) で終了する必要があります。 トレーラは、ヘッダー セグメントとトレーラ セグメントを含めたデータ セグメントの数を提供します。  
  
 トランザクション セットには、関連するセグメントのコレクションを繰り返すために必要なループを含めることができます。