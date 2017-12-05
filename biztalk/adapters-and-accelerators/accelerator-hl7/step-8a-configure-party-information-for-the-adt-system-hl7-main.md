---
title: "手順 8 a.: ADT System_hl7_main のパーティ情報を構成する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 693fda8b-9a99-4a6e-89b7-294f84676350
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9683fd02f94b96ead6817c72298338c064a14cc1
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="step-8a-configure-party-information-for-the-adt-systemhl7main"></a>手順 8 a.: ADT System_hl7_main のパーティ情報を構成します。
この手順では、ADT システム用のパーティ情報を構成します。  
  
### <a name="to-configure-the-adt-system-party-information"></a>ADT システム パーティ情報を構成するには  
  
1.  BizTalk 管理コンソールで  **BizTalk Server 管理コンソール**、順に展開**BizTalk グループ**です。 右クリック**パーティ**、 をポイント**新規**、クリックして**パーティ**です。  
  
2.  パーティのプロパティ ダイアログ ボックスで、**名前**フィールドに「 **ADT**です。 (このボックスに入力した値は、元の HL7 メッセージ インスタンス QRY^Q01.txt MSH3 を一致する必要があります)  
  
3.  コンソール ツリーでクリックして**送信ポート**です。  
  
4.  **送信ポート** ウィンドウの**名前**最初の行では、次のように選択します。 **ADT_Send**、クリックして**ok**です。  
  
5.  をクリックして**開始**、 をポイント**プログラム**、 をポイント**Microsoft BizTalk\<バージョン\>Accelerator 用 HL7**、クリックして**BTAHL7 構成エクスプ ローラー**です。  
  
6.  BTAHL7 構成エクスプ ローラーで、をクリックして、**受信確認**タブです。**受信確認の種類** **EnhancedMode**です。  
  
7.  Inboiund メッセージ ウィンドウで、受信確認プロパティの**MSH15 - 受信確認の種類をそのまま使用** **AL**です。  
  
8.  受信確認プロパティ ウィンドウの**MSH16 - アプリケーションの受信確認の種類** **NE**です。  
  
9. をクリックして**保存**、BTAHL7 構成エクスプ ローラーを閉じます。  
  
 進みます[手順 8B: HI システム用のパーティ情報を構成する](../../adapters-and-accelerators/accelerator-hl7/step-8b-configure-party-information-for-the-hi-system.md)です。