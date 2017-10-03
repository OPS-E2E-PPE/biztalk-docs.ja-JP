---
title: "MSMQ アダプターとは何ですか。 | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MSMQ adapters, about MSMQ adapters
- MSMQ adapters
ms.assetid: 4f4bfe49-19fc-4195-8826-0329f17cbe94
caps.latest.revision: "24"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d5a543e2fc5db228d249b2db2c445e254384d03
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="what-is-the-msmq-adapter"></a>MSMQ アダプターとは何ですか。
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] MSMQ アダプター (MSMQ アダプター) を Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] と共に使用して、Microsoft メッセージ キュー (MSMQ) にメッセージを送受信できます。 MSMQ アダプターは Message Queuing 4.0 をサポートしています。 このアダプターは、トランザクション キューとトランザクション以外のキュー、パブリック キューと専用キュー、およびローカル キューとリモート キューで動作します。 また、MSMQ アダプターでは、4 MB を超えるサイズの大きいメッセージがサポートされているので、リモート トランザクションの読み込みやサブキューからの読み込みなどのメッセージ キュー 4.0 機能にアクセスできます。  
  
 BizTalk Server のインストールを [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] にアップグレードしても、MSMQ 用の BizTalk Server 2009 アダプターは削除されません。 ただし、[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] で新しいバージョンの MSMQ アダプターがインストールされるので、MSMQ 用の BizTalk Server 2009 アダプターは安全にアンインストールできます。アンインストールしたら、このバージョンのアダプターのディレクトリ構造を手動で削除できます。