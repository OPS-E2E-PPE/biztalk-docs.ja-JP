---
title: '[定義] タブをバッチ処理 |Microsoft ドキュメント'
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
ms.openlocfilehash: 2270625a6e4512f2a99bea7a06812b601b48d44c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204514"
---
# <a name="batch-definition-tab"></a>[バッチの定義] タブ
使用する、**バッチ定義**] タブの [受信バッチ処理、バッチを有効にする/、バッチをバッチ処理を送信バッチ処理の利用可能なスキーマを選択します。  
  
 **BTAHL7 構成エクスプ ローラー**  ダイアログ ボックスで、**バッチ定義** タブで、次の操作します。  
  
|プロパティ|目的|  
|--------------|----------------|  
|**断片化が必要**|以下のオプションの 1 つを選択します。<br /><br /> -   **[はい]** です。 断片化を有効にします。<br />-   **いいえ**です。 断片化を無効にします。 **注:** 、新しいパーティの**断片化のために必要な**の既定値は**いいえ**です。|  
|**必要な回復可能なインターチェンジのサポート**|以下のオプションの 1 つを選択します。<br /><br /> -   **True**です。 回復可能なインターチェンジ サポートできるようにします。<br />-   **FALSE**です。 回復可能なインターチェンジのサポートを無効にします。 **注:** 、新しいパーティの**断片化のために必要な**の既定値は**FALSE**場合にのみ有効との値**断片化のために必要な**は**いいえ**です。|  
|**メッセージを選択します。**|使用可能なメッセージ ウィンドウから、バッチとして送信し、右矢印を移動するメッセージの種類を選択 (**>>**)。<br /><br /> 受信確認メッセージをバッチ処理するには、ACK メッセージの種類を追加する必要があります。 これを行う ACK メッセージ スキーマを展開することによりします。|  
|**メッセージの受信確認を選択します。**|対象となるメッセージの種類を選択して[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]バッチとして利用可能なメッセージの Ack ウィンドウから、受信確認を送信し、右矢印を移動する (**>>**)。|