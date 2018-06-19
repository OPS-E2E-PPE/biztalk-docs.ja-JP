---
title: 災害復旧の BizTalk サーバーを準備する |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 14c2c25d-30c5-4e90-a744-f084befa2c1d
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9379136f0845c7c4c987170747a28bd3c50206c4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22302146"
---
# <a name="preparing-the-disaster-recovery-biztalk-servers"></a>災害復旧の BizTalk サーバーを準備します。
インストール[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]推奨事項に従い、障害復旧サイトで実行時のサーバー [BizTalk Server 2010 インストールおよびアップグレード ガイド](http://go.microsoft.com/fwlink/?LinkID=194815)(http://go.microsoft.com/fwlink/?LinkID=194815)。 これらの構成[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ランタイム サーバーの BizTalk 構成ウィザードを使用して、実稼働の BizTalk グループに参加させます。 構成するときに、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] (災害復旧のエンタープライズ シングル サインオン マスター シークレット サーバーを含む)、災害復旧サイト サーバーの実行時間を確認します。  
  
-   選択**いいえ**「はこのマスター シークレット サーバーですか」という質問をする  
  
-   選択**結合**の質問に「たい作成したり、BizTalk Server グループに参加しますか?」  
  
 構成した後、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]実行時の障害復旧サーバーでは、実稼働サイトのホスト インスタンスに対応しているが、これらのホスト インスタンスを開始できません災害復旧サイトで BizTalk ホスト インスタンスを作成します。 たとえば、実稼働サイトでは 3 つのホスト**送信**、**受信**、および**オーケストレーション**server1、server2、および server3 インスタンスは、対応する 3 つの作成DRserver1、DRserver2、DRserver3 上のインスタンスをホストします。  
  
> [!NOTE]  
>  すべて[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]-Windows サービス、BizTalk ホスト インスタンスと障害復旧サイトでルール エンジンのサービスする必要があります設定する「無効」にサービス マネージャーで、障害復旧サイトが、処理を実行するを防ぐためで関連します。  
  
 インストールして構成する数が異なる[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]実稼働環境で実行しているよりも、障害復旧サイトでの実行時のサーバー。 障害復旧イベントが発生した場合、災害復旧サイト内のサーバーを過負荷を避けるため、ただし、このアプローチをとる場合は、注意を使用します。 結合するスクリプトを実行できます、一連のデータベースで表される BizTalk グループが完全に復元され、BizTalk グループのすべての必要なシステム変更が実行される、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] BizTalk グループにサーバーの実行時間。