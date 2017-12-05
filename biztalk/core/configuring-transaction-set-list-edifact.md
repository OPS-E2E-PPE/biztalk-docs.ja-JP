---
title: "トランザクション セットの構成 (EDIFACT) のリスト |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b03ace75-70bf-47c9-9a94-df813d7cab1e
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a95feac48f7cb5137e95a34bf46c38811bb75c51
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="configuring-transaction-set-list-edifact"></a>トランザクション セットの一覧の構成 (EDIFACT)
BizTalk Server では、含まれているまたは EDI インターチェンジを処理中に除外する必要がありますは常にトランザクション セットのリストを定義することができます。 ここでは、トランザクション セットの一覧を作成する方法について説明します。  
  
> [!IMPORTANT]
>  プロパティは無効では、このページをオフにした場合でも、**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信メッセージを処理する**チェック ボックスを作成するパーティを作成するときに、アグリーメント。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-configure-a-transaction-set-list"></a>トランザクション セットの一覧を構成するには  
  
1.  EDIFACT」の説明に従ってエンコード アグリーメントを作成する[を構成する一般的な設定 (EDIFACT)](../core/configuring-general-settings-edifact.md)です。 既存のアグリーメントを更新するでアグリーメントを右クリックし、**パーティとビジネス プロファイル** ページで、をクリックして**プロパティ**です。  
  
2.  一方向アグリーメント タブの下にある**トランザクション セットの設定**セクションで、**トランザクション セットの一覧**です。  
  
3.  選択**一覧からトランザクション セットのサポート**を常に処理する必要があるトランザクション セットの一覧を作成する場合はオプションです。  
  
    > [!NOTE]
    >  通常、特定のトランザクションの種類を持つインターチェンジ (APERAK など) を受信する場合は、このオプションを使用します。 そのような場合は、そのトランザクションの種類を一覧に追加し、他の種類のトランザクション セットがまったく処理されないようにします。  
  
4.  選択**一覧からトランザクション セットを除外する**を処理する必要がないトランザクション セットの一覧を作成する場合はオプションです。  
  
    > [!NOTE]
    >  このオプションは、トランザクションの種類が変化したインターチェンジを受信する場合に使用します。 この場合、トランザクション セットを取得しない一覧にトランザクションの種類を追加します。  
  
5.  空のセルをクリックして、 **UNH2.1**列しトランザクション セットを除外の対象をサポートする種類のドロップダウンを選択します。  
  
6.  削除するトランザクションの種類の一覧からトランザクションの種類の行を選択し、 をクリックして**削除**です。  
  
7.  をクリックして**適用**構成を続行する前に、変更を受け入れるか、をクリックする**OK**を変更を検証し、ダイアログ ボックスを閉じます。  
  
## <a name="see-also"></a>参照  
 [トランザクション セットの設定を構成する (EDIFACT)](../core/configuring-transaction-set-settings-edifact.md)