---
title: FRR 遅延タイムアウトの設定 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- FIN Response Reconciliation, configuring delay time-out
ms.assetid: 62209bf6-56c8-483a-96d5-328bffc8b680
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 42e141f1c2c3afff1049556c5bc041711695e9ca
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529982"
---
# <a name="setting-the-frr-delay-time-out"></a>FRR 遅延タイムアウトの設定
無期限に FNN 応答を待機するはありませんが、いくつかの期間の後にタイムアウトに FRR オーケストレーションを構成する必要があります。 タイムアウト期間が経過すると、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]カスタム タイムアウト ハンドラーに、タイムアウト メッセージを発行します。  
  
### <a name="to-set-the-frr-delay-time-out"></a>FRR 遅延タイムアウトを設定するには  
  
1.  をクリックして**開始**、 をクリックして**実行**、型**regedit**、順にクリックします**OK**します。  
  
2.  レジストリ エディターの左側のウィンドウでは、SWIFT/FRR のマイ コンピューター/HKEY_LOCAL_MACHINE/ソフトウェア/Microsoft/BizTalk アクセラレータに移動します。  
  
    > [!IMPORTANT]
    >  ロールは、[ロール] ノードで定義されているワークフロー内の位置に追加されます。 その位置を変更するには、8 [ロール] ノード内のロールの順序を変更する手順を実行する必要があります。  
  
3.  レジストリ エディターの右側のウィンドウでダブルクリック**DelayTimeout**します。  
  
4.  **DWORD 値の編集** ダイアログ ボックスで、**値データ**ボックスに、16 進形式でタイムアウト期間を入力します。  
  
    > [!NOTE]
    >  既定値、 **FRR DelayTimeout**プロパティが 600 秒 (258 16 進数)。  
  
5.  **[OK]** をクリックします。