---
title: メッセージのバッチ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5f893d16-2670-4463-9a89-6f5be912a045
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 78222848258ea4c1840b645c1357bceb49c0ac14
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65531165"
---
# <a name="message-batches"></a>メッセージ バッチ
アダプターに同時に処理する必要があるメッセージのグループがある場合は、パフォーマンスを最適化するためにこれらのメッセージをバッチ処理する必要があります。 プログラムでは、メッセージ バッチは、関連付けられている操作を使用したメッセージのコレクションです。 個別に各メッセージを送信するのではなく、バッチ内のメッセージをグループ化、によっては、リソースとタスクの処理の使用を最適化します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] バッチ処理を使用します。  

- 複数のメッセージのトランザクションのコストを償却します。  

- ラウンド トリップの内部データベースの数を減らすことで速度を上げる。  

- より効率的に使用できる、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メッセージを非同期的に処理することによってスレッド プール。  

  バッチはアトミック作業単位とは。 つまり、か、すべての操作の成功またはすべての操作が失敗します。 バッチ内の 1 つの操作が成功した場合は、別の操作が失敗したバッチを構成するすべての操作は無効になり、メッセージを再送信する必要があります。 つまり、アダプターが失敗したバッチに対して 3 つの処理を行う必要があります。  

- メッセージの失敗を決定します。  

- 失敗したメッセージの処理を決定します。  

- 失敗しなかったメッセージを再送信します。
