---
title: レッスン 2:ビジネス ルールの作成ツールを使用して、展開の確認 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- business rules, verifying
- verifying, business rules
- verifying, Business Rule Composer tool
- business rules, Business Rule Composer tool
- Business Rule Composer tool
ms.assetid: 337dc469-cf9e-406b-90ae-0f580b17d7c9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eee5d380c47d429f5a09343b6157cdeab8e5fba6
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530368"
---
# <a name="lesson-2-confirming-the-deployment-using-the-business-rule-composer-tool"></a>レッスン 2:展開をビジネス ルール作成ツールを使用して確認します。
このレッスンでは、ビジネス ルール作成ツールは、ボキャブラリを作成し、ポリシーの展開を確認します。 ボキャブラリは、ルールの合成で使用するボキャブラリ要素のコレクションです。 ポリシーとはバージョン管理されたビジネス ルールのコレクションです。  
  
### <a name="to-confirm-the-deployment-using-the-business-rule-composer-tool"></a>ビジネス ルール作成ツールを使用して、展開を確認するには  
  
1.  開始**ビジネス ルール作成ツール**BizTalk Server でします。  
  
2.  [ルール ストアを開く] ダイアログ ボックスで、 **OK**します。  
  
3.  ビジネス ルール作成ツールのファクト エクスプローラ ペインでを確認、ファクト エクスプ ローラーに必要なボキャブラリが表示されること、次の図に示すようにします。  
  
     ![](../../adapters-and-accelerators/accelerator-swift/media/tut2-scrn2.gif "Tut2_scrn2")  
  
4.  ポリシー エクスプ ローラーでは、ビジネス ルール作成ツールで、次のポリシーが展開されていることを確認します。  
  
     MT103_Master_Policy  
  
     MT103_Validation_Policy  
  
     SWIFT_NetworkRule149_Policy  
  
     SWIFT_NetworkRule150_Policy  
  
     SWIFT_NetworkRule151_Policy  
  
     SWIFT_NetworkRule175_Policy  
  
     SWIFT_NetworkRule2_Policy  
  
     SWIFT_NetworkRule201_Policy  
  
     SWIFT_NetworkRule202_Policy  
  
     SWIFT_NetworkRule203_Policy  
  
     SWIFT_NetworkRule204_Policy  
  
     SWIFT_NetworkRule205_Policy  
  
     SWIFT_NetworkRule206_Policy  
  
     SWIFT_NetworkRule207_Policy  
  
     SWIFT_NetworkRule209_Policy  
  
     SWIFT_NetworkRule210_Policy  
  
     SWIFT_NetworkRule212_Policy  
  
     SWIFT_NetworkRule213_Policy  
  
     SWIFT_NetworkRule215_Policy  
  
     SWIFT_NetworkRule216_Policy  
  
     SWIFT_NetworkRule217_Policy  
  
     SWIFT_NetworkRule218_Policy  
  
     SWIFT_NetworkRule244_Policy  
  
     SWIFT_NetworkRule245_Policy  
  
     SWIFT_NetworkRule81_Policy  
  
     SWIFT_PartyIdentifier_Policy  
  
     SWIFT_Reference_Policy  
  
### <a name="to-view-a-policy"></a>ポリシーを表示するには  
  
1. ビジネス ルール作成ツールの [ポリシー エクスプ ローラー] ウィンドウで、 **SWIFT_NetworkRule149_Policy**を展開し、展開、**バージョン 1.0-展開済み**ノード。  
  
2. ダブルクリックして、 **Validate_MT103**ノードを開きます。  
  
    ポリシーは、画面の右側にあるエディター ウィンドウが開きます。  
  
   続行する[モジュール 7。有効なフラット ファイル インスタンスをテスト](../../adapters-and-accelerators/accelerator-swift/module-7-testing-a-valid-flat-file-instance.md)します。