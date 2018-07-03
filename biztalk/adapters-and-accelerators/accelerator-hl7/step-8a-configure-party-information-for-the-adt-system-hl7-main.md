---
title: '手順 8 a: ADT _hl7_main 用にパーティ情報の構成 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 693fda8b-9a99-4a6e-89b7-294f84676350
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f407f549404744d76eccdfe1af47f12cbb64ef82
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971163"
---
# <a name="step-8a-configure-party-information-for-the-adt-systemhl7main"></a>手順 8 a: ADT _hl7_main 用にパーティ情報を構成します。
この手順では、ADT System 用のパーティ情報を構成します。  
  
### <a name="to-configure-the-adt-system-party-information"></a>ADT System パーティ情報を構成するには  
  
1. BizTalk 管理コンソールで、 **BizTalk Server 管理**、順に展開**BizTalk グループ**します。 右クリック**パーティ**、 をポイント**新規**、 をクリックし、**パーティ**します。  
  
2. パーティのプロパティ ダイアログ ボックスでの**名前**フィールドに「 **ADT**します。 (このボックスに入力した値は、元の HL7 メッセージ インスタンス qry ^ q01.txt MSH3 を一致する必要があります)  
  
3. コンソール ツリーで、クリックして**送信ポート**します。  
  
4. **送信ポート**ウィンドウの**名前**最初の行では、次のように選択します。 **ADT_Send**、順にクリックします**OK**。  
  
5. クリックして**開始**、 をポイント**プログラム**、 をポイント**Microsoft BizTalk\<バージョン\>Accelerator 用 HL7**、順にクリックします**BTAHL7 構成エクスプ ローラー**します。  
  
6. BTAHL7 構成エクスプ ローラーでクリックして、**受信確認**タブ。**受信確認の種類**、 **EnhancedMode**します。  
  
7. Inboiund メッセージ ウィンドウで、受信確認プロパティでの**MSH15 - 受信確認の種類をそのまま使用**、 **AL**します。  
  
8. 受信確認のプロパティ ウィンドウの**MSH16 - アプリケーションの受信確認の種類**を選択します**NE**します。  
  
9. クリックして**保存**、BTAHL7 構成エクスプ ローラーを閉じます。  
  
   続行する[手順 8 b: HI System 用にパーティ情報を構成する](../../adapters-and-accelerators/accelerator-hl7/step-8b-configure-party-information-for-the-hi-system.md)します。