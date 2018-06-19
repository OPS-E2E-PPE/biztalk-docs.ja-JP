---
title: FRR 遅延タイムアウトの設定 |Microsoft ドキュメント
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
ms.openlocfilehash: fbf4c08984876627c0f11f935b0be3e32769b5f7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214002"
---
# <a name="setting-the-frr-delay-time-out"></a>FRR 遅延タイムアウトの設定
これは待機しません FNN 応答を無期限にようにいくつかの期間の後にタイムアウトに FRR オーケストレーションを構成する必要があります。 タイムアウト期間が経過すると、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]タイムアウトのカスタム ハンドラーにタイムアウトになったメッセージを公開します。  
  
### <a name="to-set-the-frr-delay-time-out"></a>FRR 遅延タイムアウトを設定するには  
  
1.  をクリックして**開始**、 をクリックして**実行**、型**regedit**、順にクリック**ok**です。  
  
2.  レジストリ エディターの左側のウィンドウでは、SWIFT/FRR のマイ コンピューター/HKEY_LOCAL_MACHINE/ソフトウェア/Microsoft/BizTalk Accelerator に移動します。  
  
    > [!IMPORTANT]
    >  ロールは、[ロール] ノードで定義されている、ワークフロー内の位置に追加されます。 その位置を変更するには、手順 8 を実行し、[ロール] ノード内のロールの順序を変更する必要があります。  
  
3.  レジストリ エディターの右側のウィンドウでダブルクリック**DelayTimeout**です。  
  
4.  **DWORD 値の編集** ダイアログ ボックスで、**値のデータ**ボックスに、16 進形式でタイムアウト期間を入力します。  
  
    > [!NOTE]
    >  既定値、 **FRR DelayTimeout**プロパティは 600 秒 (258 16 進数)。  
  
5.  **[OK]** をクリックします。