---
title: "手順 13: が作成し、ポートの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ports, creating
- message enrichment tutorial, ports
- creating, ports
- configuring, ports
- ports, configuring
ms.assetid: cc0540d7-46fc-4d9f-bcf3-0b0e0179fd51
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c1b18e5b7addf1bae390dd541b84d17bd94023d
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="step-13-create-and-configure-ports"></a>手順 13: を作成し、ポートを構成します。
このステップでは、ポート構成ウィザードを使用して作成し、オーケストレーション デザイナーでポートを構成します。 オーケストレーションの送信し、ビジネス プロセスからメッセージを送受信ポートを指定します。 各ポートには、種類、方向、およびバインドします。 プロパティは、通信、通信のパターン、元の場所の方向を一緒に決定[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]を送信または受信メッセージとの通信が行われる方法です。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]送信ポートとして最小下位層プロトコル (MLLP) アダプターを使用します。 MLLP アダプターは、他のラボ アプリケーションなどのアプリケーション、保険アプリケーションは、従来の基幹業務アプリケーションとのインターフェイスに TCP ソケット通信を使用します。 MLLP 送信アダプターを表す、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]はアダプター。  
  
-   カスタマイズします。 アダプターにのみ付属して[!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)]に付属して BizTalk Server ではなく、します。  
  
-   プロトコル/トランスポート。 アダプターは、アプリケーションまたはデータ アダプターではありません。  
  
-   静的です。 アダプターの構成では、カスタム ユーザー インターフェイスは含まれません。  
  
-   非同期です。 アダプターがすべてのアダプターのパフォーマンスを向上できるメッセージング エンジン スレッドをブロックしていないを[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ホストします。  
  
-   非トランザクションです。 アダプターはトランザクション処理された受信または送信[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]アダプター。  
  
-   正規です。 アダプターは、別のアプリケーション プロセスでは実行されません。  
  
-   一方向と双方向です。 アダプターは、相互作用の一方向および要求-応答/送信請求-応答の両方のモードをサポートします。  
  
 MLLP アダプターでは、個々 のメッセージを送信したり、バッチ内のメッセージを送信することができます。 MLLP メッセージの先頭がラッパー文字、16 進 0x0b (とも呼ばれる、ブロックの開始] または [SB 文字) でマークされているし、16 進数の 0x1c 文字 (End ブロックまたは EB 文字とも呼ばれます) の組み合わせによって、メッセージの最後をマークすぐに続く、0x0d 文字 (キャリッジ リターン)。 BTAHL7 パフォーマンス カウンターは、送信メッセージに対してこれらのラッパー文字のみをカウントします。 BTAHL7 パフォーマンス カウンターでは、メッセージを受信するときにこれらのラッパーの文字はカウントされません。  
  
> [!NOTE]
>  SB と EB 文字を検出する機能に支障があるために、標準 MLLP のプロトコルは、メッセージ ペイロードの 0x20 下にある文字を許可されません。 SB と EB の文字の値を構成、のでくれぐれもこの問題が発生した変更を行うときにできます。  
  
 この手順では、MLLP アダプターおよび SOAP アダプターを構成します。  
  
### <a name="to-create-and-configure-the-ports"></a>ポートを作成および構成するには  
  
1.  オーケストレーション デザイナーで、ドラッグ、**ポート**ツールボックスから図形をデザイン ビューの左側にあるポート画面およびで水平方向に合わせて配置されるようにドロップします、 **DoorbellReceive**図形です。  
  
2.  **ポート構成ウィザード**をクリックして**次**です。  
  
3.  **ポートのプロパティ**] ページの [、**名前**フィールドに「 **SOAPReceivePort**、クリックしてして**[次へ]**です。  
  
4.  **ポートの種類を選択して** ページで、次の情報を入力してをクリックして**次へ**を続行します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**ポートの種類名**|型**SOAPReceivePortType**です。|  
    |**通信方式**|選択**一方向**です。|  
    |**アクセスの制限**|選択**パブリック - 制限なし**です。|  
  
5.  **ポートのバインド** ページで、をクリックして**次**既定値を入力します。  
  
6.  **ポート ウィザードの完了**] ページで [**完了**です。  
  
7.  ドラッグ、**ポート**ツールボックスから図形をデザイン ビューの右側にあるポート画面およびで水平方向に合わせて配置されるようにドロップします、 **DoorbellSend**図形です。  
  
8.  使用して、**ポート構成ウィザード**場合と同様の手順 2. ~ 7. で、次のパラメーターを使用して追加の送信ポートを作成します。  
  
    |プロパティ|パラメーター|  
    |--------------|---------------|  
    |**ポートのプロパティ名**|MLLPSendPort|  
    |**ポートの種類名**|MLLPSendPortType|  
    |**通信方式**|一方向|  
    |**アクセスの制限**|パブリック - 制限なし|  
    |**ポートのバインド**|[後で指定する]|  
    |**ポートの通信方向**|常にこのポートでメッセージを送信する|  
  
9. **オーケストレーションの種類** ウィンドウで、**型**、**ポートの種類**、および**SOAPReceivePortType** を展開するノードを展開すると、**Operation_1**、クリックして**要求**です。  
  
10. **プロパティ** ウィンドウのドロップダウン リストで、**メッセージの種類**、展開**スキーマ**、クリックして**BTAHL7_Project.Doorbell**.  
  
11. **オーケストレーションの種類**ウィンドウで、展開**MLLPSendPortType**、展開**Operation_1**、順にクリック**要求**です。  
  
12. **プロパティ** ウィンドウのドロップダウン リストで、**メッセージの種類**、展開**マルチパート メッセージの種類**、クリックして**BTAHL7_Project.DoorbellFinalMessageType**です。  
  
13. **名前**フィールドに「**応答**、キーを押します**Enter**です。  
  
14. オーケストレーション デザイン ビュー サーフェイスで、をクリックして、 **DoorbellReceive**アクション図形。  
  
15. **プロパティ**] ウィンドウのドロップダウン リストで、**メッセージ**[ **DoorbellInputMessage**です。  
  
16. オーケストレーション デザイン ビュー サーフェイスで、をクリックして、 **DoorbellSend**図形です。  
  
17. **プロパティ**] ウィンドウのドロップダウン リストで、**メッセージ**[ **DoorbellFinalMessage**です。  
  
18. 緑色のハンドルをクリックして、 **SOAPReceivePort**の緑のハンドルにドラッグして、 **DoorbellReceive**受信図形の接続に、 **SOAPReceivePort** に**DoorbellReceive**図形を受信します。  
  
19. 緑色のハンドルをクリックして、 **DoorbellSend**図形し、上の緑色のハンドルにドラッグ、 **MLLPSendPort**接続先のポート、 **DoorbellSend** に送信図形**MLLPSendPort**ポートです。  
  
20. クリックして、**ソリューション エクスプ ローラー** ] タブの [オーケストレーションの種類。  
  
21. ソリューション エクスプ ローラーで右クリック**BTAHL7V22Common**、クリックして**ビルド**です。 成功メッセージが出力ウィンドウに表示されることを確認します。  
  
    > [!NOTE]
    >  成功メッセージが表示されない場合は、ソリューションをトラブルシューティングします。  
  
22. 右クリック**BTAHL7 プロジェクト**、 をクリック**展開**BTAHL7 プロジェクトを配置します。  
  
 進みます[手順 14: オーケストレーション Web サービスとして公開](../../adapters-and-accelerators/accelerator-hl7/step-14-publish-the-orchestration-as-a-web-service.md)です。  
  
## <a name="see-also"></a>参照  
 [メッセージ強化のチュートリアル](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)