---
title: バッチ スケジュール タブ |Microsoft Docs
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
ms.openlocfilehash: 5bf479425a6a0e80b75791d9b43ee0880e6ada63
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65251808"
---
# <a name="batch-schedule-tab"></a>[バッチ スケジュール] タブ
使用する、**バッチ スケジュール** タブをアクティブ化、要求、または、送信バッチを終了します。 2 つの手順から成る、送信バッチをアクティブ化: 時間ベースの構成またはメッセージが条件とし、送信バッチ処理オーケストレーションの開始をカウントします。  
  
 構成できる[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]を使用して、送信バッチを作成するには、時間ベースまたはメッセージの数の条件またはその両方の組み合わせ。 バッチ アクティベーション条件の設定は省略可能です。 指定しない場合、バッチを手動でアクティブ化できます。 時間ベースを使用してバッチをアクティブ化またはメッセージの数の条件にする場合は、バッチをアクティブ化する前にこれらの条件を指定する必要があります。  
  
 **BTAHL7 構成エクスプ ローラー**  ダイアログ ボックスで、**バッチ スケジュール** タブで、次の操作を行います。  
  
|プロパティ|目的|  
|--------------|----------------|  
|**時間前に、の最初のバッチします。**|最初のバッチを開始する前に時間数を入力します。<br /><br /> バッチのコントロールとしてメッセージの数を選択すると、このオプションは使用できません。|  
|**後のバッチを繰り返す**|以下のオプションの 1 つを選択します。<br /><br /> -                   **時間**します。 バッチ処理の繰り返しの前に待機する時間数を入力します。<br /><br /> -                   **メッセージ**します。 次のバッチを開始する前に処理するメッセージの数を入力します。|  
|**バッチのコントロール**|次のオプションを使用します。<br /><br /> -                   **スケジュールの開始**:バッチ スケジュールを開始するには、このオプションを選択します。<br /><br /> -                   **今すぐ送信**:バッチ処理をすぐに開始するには、このオプションを選択します。 これよりも優先されます、**最初のバッチの前に時間**と**後にバッチを繰り返す**設定。<br /><br /> -                   **スケジュールの終了**:現在のバッチ スケジュールを停止するには、このオプションを選択します。 これにより、現在のバッチが完了するとして、バッチ オーケストレーションを停止します。|