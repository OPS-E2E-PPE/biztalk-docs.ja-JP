---
title: MSMQ アダプターとは何ですか。 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MSMQ adapters, about MSMQ adapters
- MSMQ adapters
ms.assetid: 4f4bfe49-19fc-4195-8826-0329f17cbe94
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e58081f9ad39b3c8964472fda39120fa238e5397
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65242937"
---
# <a name="what-is-the-msmq-adapter"></a>MSMQ アダプターとは何ですか。
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] MSMQ アダプター (MSMQ アダプター) を Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] と共に使用して、Microsoft メッセージ キュー (MSMQ) にメッセージを送受信できます。 MSMQ アダプターは Message Queuing 4.0 をサポートしています。 このアダプターは、トランザクション キューとトランザクション以外のキュー、パブリック キューと専用キュー、およびローカル キューとリモート キューで動作します。 また、MSMQ アダプターでは、4 MB を超えるサイズの大きいメッセージがサポートされているので、リモート トランザクションの読み込みやサブキューからの読み込みなどのメッセージ キュー 4.0 機能にアクセスできます。  
  
 BizTalk Server に、BizTalk Server のインストールをアップグレードした場合、MSMQ 用の BizTalk Server 2009 アダプターは削除されません。 BizTalk Server では、MSMQ アダプターの新しいバージョンがインストールされる、ため、msmq、BizTalk Server 2009 アダプターを安全にアンインストールし、アダプターのこのバージョンのディレクトリ構造を手動で削除できます。