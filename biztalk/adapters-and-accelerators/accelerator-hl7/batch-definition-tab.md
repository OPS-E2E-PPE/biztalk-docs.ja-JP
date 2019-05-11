---
title: バッチ処理の定義 タブ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- btahl7.configurationexplorer.tab.batchdefinition
helpviewer_keywords:
- Batch Definition tab [Configuration Explorer]
- batching, configuring
- configuring, batching
ms.assetid: fe8685ef-5de5-4337-8691-8e4094056ace
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 70d06bb7832d42264d90d0edd63faf5d747bf849
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65247675"
---
# <a name="batch-definition-tab"></a>[バッチの定義] タブ
使用する、**バッチ定義**タブで受信バッチ処理、バッチを有効にする/バッチ アウト、バッチ処理して、送信バッチ処理の利用可能なスキーマを選択します。  

 **BTAHL7 構成エクスプ ローラー**  ダイアログ ボックスで、**バッチ定義** タブで、次の操作を行います。  


|                   プロパティ                   |                                                                                                                                                            目的                                                                                                                                                            |
|----------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|          **必要な断片化**          |                                                           以下のオプションの 1 つを選択します。<br /><br /> -   **[はい]** します。 断片化を有効にします。<br />-   **いいえ**します。 断片化を無効にします。 **注:** 新しいパーティに対して**断片化のために必要な**の既定値は**いいえ**します。                                                           |
| **必要な回復可能なインターチェンジのサポート** | 以下のオプションの 1 つを選択します。<br /><br /> -   **True**します。 回復可能なインターチェンジのサポートを有効にするには<br />-   **FALSE**します。 回復可能なインターチェンジのサポートを無効にします。 **注:** 新しいパーティに対して**断片化のために必要な**の既定値は**FALSE**場合のみ有効ですしの値**断片化のために必要な**は**いいえ**。 |
|             **メッセージを選択します。**              |                              使用可能なメッセージ ウィンドウから、バッチとして送信し、右矢印を移動 をクリックするメッセージの種類を選択します (**>>**)。<br /><br /> 受信確認メッセージをバッチ処理するには、ACK メッセージの種類を追加する必要があります。 ACK メッセージ スキーマを展開する。 これを行います。                              |
|      **メッセージの受信確認を選択します。**      |                               対象となるメッセージの種類を選択します。[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]使用可能なメッセージの Ack ウィンドウで、バッチとして受信確認を送信し、右矢印を移動 をクリックして (**>>**)。                                |

