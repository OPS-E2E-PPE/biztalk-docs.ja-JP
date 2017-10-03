---
title: "検証の構成 (EDIFACT インターチェンジの設定) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 55820ebc-fe21-48a3-8985-1bf4184176ac
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f87e762177e2938deaa957035e255af3f0d40eab
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-validation-edifact-interchange-settings"></a>検証を構成する (EDIFACT インターチェンジの設定)
このセクションでは、重複する制御番号が処理されないようにする方法について説明します。  
  
> [!IMPORTANT]
>  プロパティは無効では、このページをオフにした場合でも、**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信メッセージを処理する**チェック ボックスを作成するパーティを作成するときに、アグリーメント。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-configure-duplicate-validation"></a>重複する検証を構成するには  
  
1.  EDIFACT」の説明に従ってエンコード アグリーメントを作成する[を構成する一般的な設定 (EDIFACT)](../core/configuring-general-settings-edifact.md)です。 既存のアグリーメントを更新するでアグリーメントを右クリックし、**パーティとビジネス プロファイル** ページで、をクリックして**プロパティ**です。  
  
2.  一方向アグリーメント タブの下にある**インターチェンジの設定**セクションで、**検証**です。  
  
3.  選択、**インターチェンジ制御番号 (UNB5)**受信パイプラインによる重複インターチェンジのブロックを有効にする チェック ボックスです。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、このオプションをオンにした場合、受信したインターチェンジのインターチェンジ制御番号が、受信した他のインターチェンジのインターチェンジ制御番号と重複していないかどうかがチェックされます。 一致した制御番号が検出された場合、受信パイプラインはインターチェンジを処理しません。  
  
4.  場合**インターチェンジ制御番号 (UNB5)**がオンにした場合、**内で重複している unb5 を確認して**フィールドに、重複するインターチェンジを確認する日数を入力します。  
  
5.  選択**インターチェンジのグループ制御番号 (UNG5)**を受信パイプラインが重複するグループを処理するを防ぐためにします。  
  
6.  選択**トランザクション セット制御番号 (UNH1) グループで**を受信パイプラインが重複しているトランザクションを処理するを防ぐために設定します。  
  
7.  をクリックして**適用**構成を続行する前に、変更を受け入れるか、をクリックする**OK**を変更を検証し、ダイアログ ボックスを閉じます。  
  
## <a name="see-also"></a>参照  
 [インターチェンジの設定の構成 (EDIFACT)](../core/configuring-interchange-settings-edifact.md)