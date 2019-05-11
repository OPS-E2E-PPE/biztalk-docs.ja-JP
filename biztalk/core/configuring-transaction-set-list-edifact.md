---
title: トランザクション セットの構成 (EDIFACT) の一覧 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b03ace75-70bf-47c9-9a94-df813d7cab1e
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5768fc6dcf0e5569acb1d07db38fedc301fb566b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390624"
---
# <a name="configuring-transaction-set-list-edifact"></a>トランザクション セットの一覧の構成 (EDIFACT)
BizTalk Server では、含まれているまたは EDI インターチェンジを処理中に除外する必要がありますは常にトランザクション セットの一覧を定義することができます。 このセクションでは、一覧の設定については、トランザクションを作成する方法を提供します。  
  
> [!IMPORTANT]
>  プロパティは無効になりませんこのページをオフにした場合でも、**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信したメッセージを処理する**チェック ボックスを作成するパーティを作成するときに、。契約です。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-configure-a-transaction-set-list"></a>一覧の設定をトランザクションを構成するには  
  
1.  EDIFACT エンコード アグリーメントを」の説明に従って作成[を構成する一般的な設定 (EDIFACT)](../core/configuring-general-settings-edifact.md)します。 既存のアグリーメントを更新するでアグリーメントを右クリックし、**パーティとビジネス プロファイル**ページ、およびクリックして**プロパティ**します。  
  
2.  一方向アグリーメント タブで、**トランザクション セットの設定**セクションで、**トランザクション セットの一覧**します。  
  
3.  選択**一覧からトランザクション セットのサポート**オプションを常に処理する必要があるトランザクション セットの一覧を作成する場合。  
  
    > [!NOTE]
    >  特定のトランザクションの種類、インターチェンジを受信する場合は、このオプションを使用すると、APERAK があるとします。 その場合は、ことを一覧にトランザクションの種類の他の種類のトランザクション セットが処理されないようにまったくを追加します。  
  
4.  選択**一覧からトランザクション セットを除外する**を処理する必要がないトランザクション セットの一覧を作成する場合はオプションです。  
  
    > [!NOTE]
    >  さまざまなトランザクションの種類でインターチェンジを受信する場合は、このオプションを使用します。 トランザクションの種類を追加する場合、すべてのトランザクションを受け取りませんリストに設定します。  
  
5.  空のセルをクリックして、 **UNH2.1**列ドロップダウンの選択からトランザクション セットの種類の除外の対象をサポートするとします。  
  
6.  トランザクションの種類を一覧から削除するトランザクションの種類の行を選択し、をクリックして**削除**します。  
  
7.  をクリックして**適用**構成では、続行する前に、変更を受け入れるか、をクリックする**OK**変更を検証し、ダイアログ ボックスを閉じます。  
  
## <a name="see-also"></a>参照  
 [トランザクション セットの設定を構成する (EDIFACT)](../core/configuring-transaction-set-settings-edifact.md)