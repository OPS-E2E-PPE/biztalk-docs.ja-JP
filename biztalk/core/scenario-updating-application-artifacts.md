---
title: 'シナリオ: アプリケーション アイテムの更新 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, artifacts
- updating, artifacts
- artifacts, examples
- updating, examples
- examples, updating
- artifacts, updating
ms.assetid: 76833df3-2330-48af-84d8-731028b192ff
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e95e6a66fb0e6bccc1fcc2fb4a7664538e50d3e2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269538"
---
# <a name="scenario-updating-application-artifacts"></a>シナリオ : アプリケーション アイテムの更新
実稼働環境に展開されたアプリケーションのアイテムを更新する場合、基本的なシナリオとして次の 2 つがあります。  
  
-   オーケストレーションが長時間トランザクションを処理する場合、または送信請求 - 応答ポートからの応答を待機している場合に、そのオーケストレーションを新しいバージョンに更新する。  
  
-   メッセージ処理を完了させることが目的でない場合に行われる、より一般的な更新のケース。たとえば、スキーマまたはマップを新しいバージョンに更新する場合など。  
  
 一般的な更新のケースでは、ビジネス要件の変更などに対応するために、アイテムを新しいバージョンに更新することができます。 これは比較的簡単なシナリオであり、元のアイテムを更新されたアイテムで上書きできます。 必要な手順の一覧は、次を参照してください。[チェックリスト: BizTalk アプリケーション内のアイテムの更新](../core/checklist-update-the-artifacts-in-a-biztalk-application.md)です。  
  
 2 番目のシナリオはより複雑です。 この場合、既存のオーケストレーションがメッセージ処理を完了できるようにする必要があります。 同時に、既存のオーケストレーションが新しいメッセージを処理できないようにする必要があります。 代わりに、更新されたバージョンのオーケストレーションによる引き継ぎが必要になります。 これを行うには、更新されたオーケストレーションを含むアセンブリを元のバージョンと同じ BizTalk アプリケーションに展開し、両方のオーケストレーションを同時に実行します  (新しいアセンブリには、元のオーケストレーションを含むアセンブリとは異なるバージョン番号が必要です。バージョン番号が同一の場合、新しいアセンブリを同じ BizTalk グループに展開することができません)。次に、元のバージョンの参加を解除し、新しいメッセージがこのオーケストレーションに回送されないようにします。その後、更新されたバージョンを開始し、新しいメッセージがすべてこのバージョンに送信されるようにします。 元のバージョンによるメッセージ処理がすべて完了したら、元のバージョンを展開解除することができます。 これらのタスクの実行方法の詳細については、次を参照してください。[オーケストレーションをアップグレードする方法](../core/how-to-upgrade-an-orchestration.md)です。  
  
 次の図は、標準のオーケストレーション並列展開を示しています。  
  
 ![サイド バイ サイド展開シナリオ](../core/media/ebiz-depl-sidebyside-scenario.gif "ebiz_depl_sidebyside_scenario")  
  
## <a name="see-also"></a>参照  
 [アプリケーションの展開と管理のシナリオ](../core/application-deployment-and-management-scenarios.md)   
 [アプリケーションを更新するための重要な考慮事項](../core/important-considerations-for-updating-applications.md)