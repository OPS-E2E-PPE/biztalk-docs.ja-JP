---
title: バッチ スケジュール タブ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- btahl7.configurationexplorer.tab.batchschedule
helpviewer_keywords:
- batching, scheduling
- Batch Schedule tab [Configuration Explorer]
- scheduling batching
ms.assetid: 3792388b-6af2-41c2-8f41-bdfda7e17b2b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d870abad399dcca76c32a3a8d0e8c6637fc93284
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204490"
---
# <a name="batch-schedule-tab"></a>[バッチ スケジュール] タブ
使用する、**バッチ スケジュール** タブをアクティブ化、要求、または送信バッチを終了します。 送信バッチをアクティブ化する 2 つの手順で構成されています: 時間ベースの構成またはメッセージが条件とし、送信バッチ処理オーケストレーションの開始をカウントします。  
  
 構成することができます[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]時間ベースを使用して、送信バッチを作成またはメッセージのカウントの条件または両方の組み合わせ。 バッチ アクティベーション条件を設定することは、省略可能です。 指定しない場合、バッチを手動でアクティブ化できます。 時間ベースを使用してバッチをアクティブ化またはメッセージのカウントの条件にする場合は、バッチをアクティブ化する前にこれらの条件を指定する必要があります。  
  
 **BTAHL7 構成エクスプ ローラー**  ダイアログ ボックスで、**バッチ スケジュール** タブで、次の操作します。  
  
|プロパティ|目的|  
|--------------|----------------|  
|**時間前に、の最初のバッチします。**|最初のバッチを開始する前に時間数を入力します。<br /><br /> バッチのコントロールとしてメッセージの数を選択すると、このオプションは使用できません。|  
|**後にバッチを繰り返す**|以下のオプションの 1 つを選択します。<br /><br /> -                   **時間**です。 バッチ処理を繰り返す前に待機する時間数を入力します。<br /><br /> -                   **メッセージ**です。 次のバッチを開始する前に処理するメッセージの数を入力します。|  
|**バッチの制御**|次のオプションを使用します。<br /><br /> -                   **スケジュールの開始**: バッチ スケジュールを開始するには、このオプションを選択します。<br /><br /> -                   **今すぐ送信**: バッチ処理を直ちに開始するには、このオプションを選択します。 上書きされます。、**最初のバッチになるまで時間**と**後にバッチを繰り返して**設定します。<br /><br /> -                   **スケジュールを停止**: 現在のバッチ スケジュールを停止するには、このオプションを選択します。 これにより、現在のバッチを完了し、バッチ オーケストレーションを停止します。|