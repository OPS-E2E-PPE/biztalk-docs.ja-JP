---
title: '手順 5: ファイル アダプタを使用して、ADT システムに受信確認を配信する送信ポートの作成 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- end-to-end tutorial, send ports
- send ports, acknowledgements
- creating, send ports
- acknowledgements, send ports
- send ports, creating
ms.assetid: 565a2adf-fd86-46e3-8035-7e4748aefffc
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d6e63590c8cc84a6c6c1a7e957900aa44cdcd61c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25961840"
---
# <a name="step-5-create-a-send-port-to-deliver-acknowledgments-to-the-adt-system-using-the-file-adapter"></a>手順 5: ファイル アダプタを使用して、ADT システムに受信確認を配信する送信ポートを作成します。
この手順では、ファイル アダプターを使用して受信確認を生成する送信ポートを作成します。  
  
### <a name="to-create-the-tutorialsendackadt-send-port"></a>Tutorial_sendAck_ADT 送信ポートを作成するには  
  
1.  使用して[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]エクスプ ローラーで、作成、 \<*ドライブ*:\>\Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\End エンドツー エンド Tutorial\Tutorial_ のアクセラレータsendAck_ADT フォルダーです。  
  
2.  BizTalk Server 管理コンソールで、右クリック**送信ポート**、 をポイント**新規**、クリックして**静的な一方向送信ポート**です。  
  
3.  [送信ポートのプロパティ] ダイアログ ボックスで、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**名前**|型**Tutorial_sendAck_ADT**です。|  
    |**トランスポートの種類**|選択**ファイル**ドロップダウン リストからです。|  
    |**構成**|をクリックして**構成**を開くには、 **File トランスポートのプロパティ** ダイアログ ボックス。|  
  
4.  ファイル トランスポートのプロパティ ダイアログ ボックスで、次の操作をクリックして**OK**です。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**コピー先フォルダー**|参照 **\<** *ドライブ***:\>\Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\End エンドツー エンドのアクセラレータTutorial\Tutorial_sendAck_ADT**です。|  
    |**ファイル名**|型 **%MessageID%.txt** (拡張子 .txt に .xml 拡張子を置き換えます)。|  
  
5.  送信ポートのプロパティ] ダイアログ ボックスの**送信パイプライン**[ **BTAHL72XPipelines.BTAHL72XSendPipeline**です。  
  
6.  左側のウィンドウでをクリックして**フィルター**、し、次の操作を行います。  
  
    > [!NOTE]
    >  最初のフィルターは、受信確認メッセージをサブスクライブしていることを意味します。 2 番目のフィルターは、パブリッシャー Tutorial_ADTSystem に送信される受信確認をサブスクライブしたことを意味します。  
  
     をクリックして**OK**続行する準備ができたらです。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**プロパティ**|下のフィールドをクリックして**プロパティ**、し、 **BTS です。MessageType**ドロップダウン リストからです。|  
    |**演算子**|選択 **==** ドロップダウン リストからです。|  
    |**値**|型**http://microsoft.com/HealthCare/HL7/2X#ACK_24_GLO_DEF**です。|  
    |**グループ化**|選択**または**ドロップダウン リストからです。|  
    |**プロパティ (2 番目の行)**|下のフィールドをクリックして**プロパティ**、し、 **BTS です。MessageType**ドロップダウン リストからです。|  
    |**演算子**|選択 **==** ドロップダウン リストからです。|  
    |**値**|型**http://microsoft.com/HealthCare/HL7/2X#ACK_25_GLO_DEF です。**|  
    |**グループ化**|選択**AND**ドロップダウン リストからです。|  
    |**プロパティ**|最初のプロパティでは、下の空のボックスをクリックし、 **BTAHL7Schemas.MSH5_1**です。|  
    |**演算子**|選択 **==** ドロップダウン リストからです。|  
    |**値**|型**Tutorial_ADTSystem**です。|  
  
    > [!NOTE]
    >  BTAHL7 がファイルの格納場所に、受信確認を削除、送信ポート Tutorial_sendAck_ADT の\<*ドライブ*\>: プログラム FilesMicrosoft BizTalk <version> HL7SDKEnd エンドツー エンドのアクセラレータTutorialTutorial_sendAck_ADT です。  
  
7.  をクリックして**適用**、クリックして **[ok] です。**  
  
8.  管理コンソールで、をクリックして**送信ポート**を右クリックして**Tutorial_sendAck_ADT**、クリックして**開始**です。  
  
 進みます[手順 6: ADT を配信する送信ポートを作成 ^ A03 メッセージをファイル アダプターを使用して RX システム](../../adapters-and-accelerators/accelerator-hl7/step-6-create-send-port-to-deliver-adt^a03-message-to-rx-system-using-file.md)です。