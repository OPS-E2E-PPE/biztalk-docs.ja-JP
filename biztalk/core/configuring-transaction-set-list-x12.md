---
title: "トランザクション セットの構成一覧 (X12) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1f277318-90e9-4ad3-843a-e6128837fa2b
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 18b11ea09c7c3156aea18b95d758228e55994901
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-transaction-set-list-x12"></a>トランザクション セットの一覧の構成 (X12)
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、EDI インターチェンジの処理中に常に含めるまたは除外する必要のあるトランザクション セットの一覧を定義できます。 ここでは、トランザクション セットの一覧を作成する方法について説明します。  
  
> [!NOTE]
>  ここで説明する設定は、HIPAA インターチェンジにも当てはまります。  
  
> [!IMPORTANT]
>  プロパティは無効では、このページをオフにした場合でも、**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信メッセージを処理する**チェック ボックスを作成するパーティを作成するときに、アグリーメント。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-configure-a-transaction-set-list"></a>トランザクション セットの一覧を構成するには  
  
1.  X12 エンコード アグリーメント」の説明に従って作成[全般設定を構成する (X12)](../core/configuring-general-settings-x12.md)です。 既存のアグリーメントを更新するでアグリーメントを右クリックし、**パーティとビジネス プロファイル** ページで、をクリックして**プロパティ**です。  
  
2.  一方向アグリーメント タブの下にある**トランザクション セットの設定**セクションで、**トランザクション セットの一覧**です。  
  
3.  選択**一覧からトランザクション セットのサポート**を常に処理する必要があるトランザクション セットの一覧を作成する場合はオプションです。  
  
    > [!NOTE]
    >  通常、特定のトランザクションの種類を持つインターチェンジ (850 など) を受信する場合は、このオプションを使用します。 そのような場合は、そのトランザクションの種類を一覧に追加し、他の種類のトランザクション セットがまったく処理されないようにします。  
  
4.  選択**一覧からトランザクション セットを除外する**を処理する必要がないトランザクション セットの一覧を作成する場合はオプションです。  
  
    > [!NOTE]
    >  このオプションは、トランザクションの種類が変化したインターチェンジを受信する場合に使用します。 この場合、トランザクション セットを取得しない一覧にトランザクションの種類を追加します。  
  
5.  空のセルをクリックして、 **ST01**列しトランザクション セットを除外の対象をサポートする種類のドロップダウンを選択します。  
  
6.  削除するトランザクションの種類の一覧からトランザクションの種類の行を選択し、 をクリックして**削除**です。  
  
7.  をクリックして**適用**構成を続行する前に、変更を受け入れるか、をクリックする**OK**を変更を検証し、ダイアログ ボックスを閉じます。  
  
## <a name="see-also"></a>参照  
 [トランザクション セットの構成設定 (X12)](../core/configuring-transaction-set-settings-x12.md)