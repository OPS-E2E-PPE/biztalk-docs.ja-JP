---
title: "フォールバック検証プロパティ (EDIFACT) の構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b925d063-e24b-4cfb-acbd-dcadb511011d
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf0e103eb2e20bb64973cd207ed2a55c2f91e58d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-fallback-validation-properties-edifact"></a>フォールバック検証プロパティの構成 (EDIFACT)
このセクションでは、重複する制御番号が処理されないようにする方法について説明します。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-configure-duplicate-validation"></a>重複する検証を構成するには  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、右クリックし、**パーティ**ノードをクリックして**EDIFACT フォールバックの設定**です。  
  
2.  **EDIFACT フォールバックの設定**] ダイアログ ボックスで、 **EDIFACT アグリーメント ページ**] タブの [、**インターチェンジの設定**セクションで、[**検証**.  
  
3.  選択、**インターチェンジ制御番号 (UNB5)**受信パイプラインによる重複インターチェンジのブロックを有効にする チェック ボックスです。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、このオプションをオンにした場合、受信したインターチェンジのインターチェンジ制御番号が、受信した他のインターチェンジのインターチェンジ制御番号と重複していないかどうかがチェックされます。 一致した制御番号が検出された場合、受信パイプラインはインターチェンジを処理しません。  
  
4.  場合**インターチェンジ制御番号 (UNB5)**がオンにした場合、**内で重複している unb5 を確認して**フィールドに、重複するインターチェンジを確認する日数を入力します。  
  
5.  選択**インターチェンジのグループ制御番号 (UNG5)**を受信パイプラインが重複するグループを処理するを防ぐためにします。  
  
6.  選択**トランザクション セット制御番号 (UNH1) グループで**を受信パイプラインが重複しているトランザクションを処理するを防ぐために設定します。  
  
7.  をクリックして**適用**構成を続行する前に、変更を受け入れるか、をクリックする**OK**を変更を検証し、ダイアログ ボックスを閉じます。  
  
## <a name="see-also"></a>参照  
 [インターチェンジ処理に対する EDIFACT フォールバック アグリーメントのプロパティを構成します。](../core/configuring-edifact-fallback-agreement-properties-for-interchange-processing.md)