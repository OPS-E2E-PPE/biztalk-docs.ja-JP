---
title: EDI トランザクション セット/メッセージの構造体要素 |Microsoft Docs
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
ms.openlocfilehash: 90a76be641269193386d6fb7443bcd7daaed28f8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350178"
---
# <a name="edi-transaction-set-message-structural-element"></a>EDI トランザクション セット/メッセージの構造体要素
トランザクション セット (X12 エンコード) またはメッセージ (EDIFACT エンコード) には、メッセージ データを構成するセグメントが含まれています。 トランザクション セットは、ヘッダー、データ セグメントのコレクション、およびトレーラで構成されています。 トランザクションの処理に必要なすべての詳細情報は、トランザクション セット内で使用できます。  
  
 トランザクション セットは、ST トランザクション セット ヘッダー (X12 の場合) または UNH メッセージ ヘッダー (EDIFACT の場合) で開始する必要があります。 また、SE トランザクション セット トレーラ (X12 の場合) または UNT メッセージ トレーラ (EDIFACT の場合) で終了する必要があります。 トレーラは、ヘッダー セグメントとトレーラ セグメントを含めたデータ セグメントの数を提供します。  
  
 トランザクション セットには、関連するセグメントのコレクションを繰り返すために必要なループを含めることができます。