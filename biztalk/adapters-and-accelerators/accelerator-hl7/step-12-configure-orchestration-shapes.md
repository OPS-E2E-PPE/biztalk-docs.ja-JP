---
title: "手順 12: オーケストレーション図形の構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring, orchestration shapes
- orchestrations, shapes
- message enrichment tutorial, orchestrations
ms.assetid: 9388254b-2841-4489-838e-de913ceff151
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7375912c49c431c67c7ff55025cd2821374b87b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-12-configure-orchestration-shapes"></a>手順 12: オーケストレーション図形を構成します。
このステップでは、不十分な構成のスマート タグを削除するためにオーケストレーション図形の構成を完了します。 指定する**DoorbellOutputMessage**最初の変換プロセスの出力として指定する**DoorbellMap.btm**そのプロセスで使用されるマップとして。 指定する**DoorbellFinalMessage** 2 番目の出力と同じプロセスを変換およびその他のフィールドのデータを持つメッセージを拡充する式を追加します。  
  
 **前提条件:** [サポート技術情報記事 941261](http://support.microsoft.com/kb/941261)オーケストレーションの構成を設定する前に適用する必要があります。  
  
### <a name="to-configure-orchestration-shapes"></a>オーケストレーション図形を構成するには  
  
1.  オーケストレーションのデザイン ビュー サーフェイスで[!INCLUDE[vs2012](../../includes/vs2012-md.md)]をクリックして、 **ConstructMessage_1**図形です。  
  
2.  **プロパティ**ウィンドウで、をクリックして、**構築メッセージ**プロパティを選択**DoorbellOutputMessage**ドロップダウン リストを押してからから**入力**です。  
  
3.  オーケストレーション デザイン ビュー サーフェイスで、をクリックして、 **DoorbellTransform**図形の内側、 **ConstructMessage_1**図形です。 **プロパティ**ウィンドウで、をクリックして**マップ名**、属性フィールドで省略記号 (...) ボタンをクリックします。  
  
4.  変換の構成] ダイアログ ボックスで、[**既存のマップ**です。 **完全修飾マップ名**ドロップダウン リストをクリックして**BTAHL7_Project.DoorbellMap**です。  
  
5.  をクリックして**ソース**左側のウィンドウでします。  
  
6.  空のボックスをクリックして**変数名** をクリック**DoorBellInputMessage**ドロップダウン リストからです。  
  
7.  をクリックして**先**左側のウィンドウでします。  
  
8.  空のボックスをクリックして**変数名** をクリック**DoorbellOutputMessage**ドロップダウン リストからです。  
  
9. をクリックして**OK**変更を保存します。  
  
10. オーケストレーション デザイン ビュー サーフェイスで、をクリックして、 **ConstructMessage_2**図形です。  
  
11. **プロパティ**ウィンドウで、をクリックして**構築メッセージ** **DoorbellFinalMessage**ドロップダウン リスト、キーを押しますから**を入力してください**.  
  
12. オーケストレーション デザイン ビュー サーフェイスで、をクリックして、 **DoorbellFinalTransform**図形の内側、 **ConstructMessage_2**図形です。 **プロパティ**ウィンドウで、をクリックして**式**BizTalk 式エディターを開くに省略記号 (...) ボタンをクリックします。  
  
13. BizTalk 式エディターでは、テキスト フィールドをクリックし、次のテキストを貼り付けます。  
  
    ```  
    HeaderInfo = new System.Xml.XmlDocument();   
    HeaderInfo.LoadXml("<ns0:MSH_25_GLO_DEF xmlns:ns0=\"http://microsoft.com/HealthCare/HL7/2X\">  
        <MSH><MSH.2_EncodingCharacters>^~\\&</MSH.2_EncodingCharacters><MSH.3_SendingApplication>  
        <HD.0_NamespaceId>SrcApp</HD.0_NamespaceId><HD.1_UniversalId>SrcAppUid</HD.1_UniversalId>  
        </MSH.3_SendingApplication><MSH.4_SendingFacility><HD.0_NamespaceId>srcFac</HD.0_NamespaceId>  
        <HD.1_UniversalId>srcFacUid</HD.1_UniversalId></MSH.4_SendingFacility><MSH.5_ReceivingApplication>  
        <HD.0_NamespaceId>dstApp</HD.0_NamespaceId><HD.1_UniversalId>dstAppUid</HD.1_UniversalId>  
        </MSH.5_ReceivingApplication><MSH.6_ReceivingFacility><HD.0_NamespaceId>dstFac</HD.0_NamespaceId>  
        <HD.1_UniversalId>dstFacUid</HD.1_UniversalId></MSH.6_ReceivingFacility><MSH.7_DateTimeOfMessage>  
        <TS.1>200307092343</TS.1></MSH.7_DateTimeOfMessage><MSH.8_Security>sec</MSH.8_Security>  
        <MSH.9_MessageType><CM_MSG.0_MessageType>ADT</CM_MSG.0_MessageType>  
        <CM_MSG.1_TriggerEvent>A04</CM_MSG.1_TriggerEvent></MSH.9_MessageType>  
        <MSH.10_MessageControlId>msgid2134</MSH.10_MessageControlId><MSH.11_ProcessingId>  
        <PT.0_ProcessingId>P</PT.0_ProcessingId></MSH.11_ProcessingId><MSH.12_VersionId>  
       <VID_0_VersionId>2.2</VID_0_VersionId></MSH.12_VersionId></MSH></ns0:MSH_25_GLO_DEF>");  
  
    DoorbellFinalMessage.MSHSegment = HeaderInfo;  
    DoorbellFinalMessage.BodySegments = DoorbellOutputMessage;  
    DoorbellFinalMessage.ZSegments = "";  
  
    DoorbellFinalMessage(BTAHL7Schemas.MSH1) = 124;   
    DoorbellFinalMessage(BTAHL7Schemas.MessageEncoding) = 65001;  
    DoorbellFinalMessage(BTAHL7Schemas.MSH2) = "^~\\&";  
    DoorbellFinalMessage(BTAHL7Schemas.ParseError) = false;   
    DoorbellFinalMessage(BTAHL7Schemas.ZPartPresent) = false;  
    DoorbellFinalMessage(BTAHL7Schemas.SegmentDelimiter2Char) = true;  
  
    ```  
  
14. **[OK]**をクリックします。  
  
    > [!IMPORTANT]
    >  式では、"HeaderInfo.LoadXml"には、キャリッジ リターンと、式内のスペースを削除します。 "HeaderInfo.LoadXml"ステートメントは、1 つの行にする必要があります。  
  
    > [!NOTE]
    >  上記のテキストの最初のブロックは、ハード コーディングされた XML ヘッダーの例を示します。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]シリアライザーには、ヘッダー セグメントが必要です。 お客様の環境のニーズに合わせてこれらのヘッダー値をカスタマイズすることができます。 上記のテキストの 2 番目のブロックでは、マルチパート メッセージで必要な 3 つのメッセージ部分を定義します。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]シリアライザーには、マルチパート メッセージが必要です。 上記のテキストの 3 番目のブロックには、昇格させたプロパティが含まれています。 を、 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] HL7 フラット ファイル メッセージに XML メッセージをシリアル化するためにシリアライザーを調べます。  
  
 進みます[手順 13: を作成し、ポートを構成する](../../adapters-and-accelerators/accelerator-hl7/step-13-create-and-configure-ports.md)です。  
  
## <a name="see-also"></a>参照  
 [メッセージの強化のチュートリアル](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)