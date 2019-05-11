---
title: 手順 8 C:HI System 用のパーティ情報の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4ac5c113-7ee7-4009-8ca3-d263f74c7a8d
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b4b0e60ddf093017e0b40424a748eb536849d48f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65286676"
---
# <a name="step-8c-configure-party-information-for-the-hi-system"></a>手順 8 C:HI System 用のパーティ情報を構成します。
この手順では、HI System 用のパーティ情報を構成します。  

### <a name="to-configure-the-hi-system-party-information"></a>HI System パーティ情報を構成するには  

1. 右クリックし、BizTalk Server 管理コンソールで**パーティ**、 をポイント**新規**、 をクリックし、**パーティ**。  

2. パーティのプロパティ ダイアログ ボックスでの**名前**ボックスに「 **Tutorial_HISystem**します。  

3. コンソール ツリーで、クリックして**送信ポート**します。  

4. 送信ポート] ペインで、[空白のフィールドをクリックします。、**名前**列で、 **Tutorial_MllpSend**、順にクリックします**OK**します。  

5. クリックして**開始**、 をポイント**プログラム**、 をポイント**Microsoft BizTalk\<バージョン\>Accelerator 用 HL7**、順にクリックします**BTAHL7 構成エクスプ ローラー**します。  

6. BTAHL7 構成エクスプ ローラーで、選択、 **MSH マップ**タブをクリックし、次の操作を行います。  


   | プロパティ  |                                             目的                                             |
   |-----------|----------------------------------------------------------------------------------------------------|
   | **MSH3**  | 型**BTAHL7**、 **IE**、および**UUID**最初に 2 番目、および第 3 にメッセージ ボックスをそれぞれします。 |
   | **MSH5**  | 型**HI**、**システム**、および**GUID**最初に 2 番目、および第 3 にメッセージ ボックスをそれぞれします。 |
   | **MSH9**  |           型**ADT**と**A04**最初と 2 番目のメッセージ ボックスに、それぞれします。            |
   | **MSH12** |                                           型**2.4**します。                                            |
   | **MSH15** |         選択**SU**メッセージの転送が成功した後に受信確認を送信します。          |
   | **MSH16** |                            選択**NE**受信確認を送信しません。                            |


7. クリックして**保存**、BTAHL7 構成エクスプ ローラーを閉じます。  

   > [!NOTE]
   >  構成情報がこのシナリオで必要ないため、BTAHL7 インターフェイス エンジンのシステムでは、パーティ情報を作成する必要はありません。  

   続行する[手順 9。BizTalk Server の再起動](../../adapters-and-accelerators/accelerator-hl7/step-9-restart-biztalk-server.md)します。