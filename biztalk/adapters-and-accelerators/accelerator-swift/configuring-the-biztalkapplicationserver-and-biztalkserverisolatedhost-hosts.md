---
title: BizTalkApplicationServer および BizTalkServerIsolatedHost ホストの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring, hosts
- BizTalkApplicationServer host
- hosts
- BizTalkServerIsolatedHost host
ms.assetid: 17bc9f01-ff87-427d-8411-6a065814ba1e
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 462abf2b0b7f9fc0df8a1b754d0fa5803656ab88
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378528"
---
# <a name="configuring-the-biztalkapplicationserver-and-biztalkserverisolatedhost-hosts"></a>BizTalkApplicationServer および BizTalkServerIsolatedHost ホストの構成
BizTalk メッセージング サーバーには、メッセージング (送信および受信メッセージ) を制限するためには、MSMQT の送信を実行しているし、受信ハンドラー, メッセージング サーバーでのみ実行する既定のホストを構成する必要があります。  
  
### <a name="to-configure-the-default-hosts"></a>既定のホストを構成するには  
  
1.  BizTalk 管理コンソールを使用して、BizTalkApplicationServer ホストからオーケストレーション サーバーのホスト インスタンスを削除します。  
  
    -   各ホスト インスタンスを右クリックし、をクリックして**停止**します。  
  
    -   各ホスト インスタンスを右クリックし、をクリックして**削除**します。  
  
2.  BizTalk 管理コンソールを使用して、[biztalkserverisolatedhost] ホストからオーケストレーション サーバーのホスト インスタンスを削除します。  
  
    -   各ホスト インスタンスを右クリックし、[削除] をクリックします。  
  
3.  ホストを構成した後は、すべてのサーバー上のすべてのホスト インスタンスを再起動します。