---
title: BizTalkApplicationServer と BizTalkServerIsolatedHost ホストの構成 |Microsoft ドキュメント
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
ms.openlocfilehash: 8459debcd52ce990bc98adf3a2a2372206bae336
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22208802"
---
# <a name="configuring-the-biztalkapplicationserver-and-biztalkserverisolatedhost-hosts"></a>BizTalkApplicationServer と BizTalkServerIsolatedHost ホストの構成
BizTalk メッセージのサーバーには、メッセージング (送信および受信メッセージ) を制限するためには、MSMQT の送信を実行するいると、受信ハンドラー, メッセージング サーバー上でのみ実行する既定のホストを構成する必要があります。  
  
### <a name="to-configure-the-default-hosts"></a>既定のホストを構成するには  
  
1.  BizTalk 管理コンソールを使用して、BizTalkApplicationServer ホストからオーケストレーション サーバーのホスト インスタンスを削除します。  
  
    -   各ホスト インスタンスを右クリックし、をクリックして**停止**です。  
  
    -   各ホスト インスタンスを右クリックし、をクリックして**削除**です。  
  
2.  BizTalk 管理コンソールを使用して、[biztalkserverisolatedhost] ホストからオーケストレーション サーバーのホスト インスタンスを削除します。  
  
    -   各ホスト インスタンスを右クリックし、[削除] をクリックします。  
  
3.  ホストを構成した後は、すべてのサーバー上のすべてのホスト インスタンスを再起動します。