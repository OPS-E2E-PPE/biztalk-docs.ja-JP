---
title: ディザスター リカバリー BizTalk Server の準備 |Microsoft Docs
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
ms.openlocfilehash: 61e283233017723a5dbb014eae41073820a7f43d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279027"
---
# <a name="preparing-the-disaster-recovery-biztalk-servers"></a>ディザスター リカバリー BizTalk Server の準備
インストール[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、推奨事項に従い、ディザスター リカバリー サイトでの実行時サーバー [BizTalk Server 2010 インストールおよびアップグレード ガイド](http://go.microsoft.com/fwlink/?LinkID=194815)(<http://go.microsoft.com/fwlink/?LinkID=194815>)。 これらの構成[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ランタイム サーバーを BizTalk 構成ウィザードを使用して、運用環境の BizTalk グループに参加させます。 構成するときに、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] (ディザスター リカバリーのエンタープライズ シングル サインオン マスター シークレット サーバーを含む) のディザスター リカバリー サイトでの実行時のサーバーを確認します。  
  
- 選択**いいえ**「これはマスター シークレット サーバーとは」質問する  
  
- 選択**結合**の質問に"Do you want を作成または BizTalk Server グループに参加しますか?"  
  
  構成した後、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]実行時の障害回復サーバーでは、実稼働サイトのホスト インスタンスに対応していますが、これらのホスト インスタンスを起動しないが、ディザスター リカバリー サイトでの BizTalk ホスト インスタンスを作成します。 たとえば、実稼働サイトがある 3 つのホスト**送信**、**受信**、および**オーケストレーション**server1、server2 というと server3 インスタンス、対応する 3 つの作成DRserver1、DRserver2、DRserver3 上のインスタンスをホストします。  
  
> [!NOTE]
>  すべて[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]-Windows サービス、BizTalk ホスト インスタンスと、ディザスター リカバリー サイトでのルール エンジンのサービスに設定する"disabled"サービス マネージャーで、ディザスター リカバリー サイトが、処理を実行するを防ぐためになどに関連します。  
  
 インストールして構成の数が異なる[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]実稼働環境で実行しているよりも、ディザスター リカバリー サイトでの実行時のサーバー。 ディザスター リカバリーのイベントが発生した場合に、ディザスター リカバリー サイト内のサーバーをオーバー ロードを防ぐために、ただし、このアプローチを取る場合は、注意を使用します。 参加するスクリプトを実行できるデータベースのセットによって表される BizTalk グループを完全に復元され、BizTalk グループのすべての必要なシステム変更を実行、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]実行時のサーバーを BizTalk グループにします。