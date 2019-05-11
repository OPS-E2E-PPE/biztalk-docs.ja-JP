---
title: 手順 13:作成し、ポートの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ports, creating
- message enrichment tutorial, ports
- creating, ports
- configuring, ports
- ports, configuring
ms.assetid: cc0540d7-46fc-4d9f-bcf3-0b0e0179fd51
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 09113f9fb108c79630597c5e930e13651e679944
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65288946"
---
# <a name="step-13-create-and-configure-ports"></a>手順 13:作成し、ポートを構成します。
この手順では、ポート構成ウィザードを使用して作成し、オーケストレーション デザイナーでポートを構成します。 ポートは、オーケストレーションの送信し、受信メッセージとビジネス プロセスの間を指定します。 各ポートは、型、方向、およびバインドには。 プロパティの方向の通信、通信のパターン、元の場所が決定[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]を送信または受信メッセージとの通信が行われる方法です。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 送信ポートとして、最低限の下位レイヤー プロトコル (MLLP) アダプターを使用します。 MLLP アダプターでは、他のテスト アプリケーションなどのアプリケーション、保険アプリケーションは、従来の基幹業務アプリケーションとのインターフェイスに TCP ソケット通信を使用します。 MLLP 送信アダプターを表す、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]はアダプター。  

- カスタマイズします。 アダプターにのみ付属[!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)]配布 BizTalk Server ではなく、します。  

- プロトコル/トランスポート。 アダプターは、アプリケーションまたはデータ アダプターではありません。  

- 静的です。 アダプターの構成では、カスタム ユーザー インターフェイスは関与しません。  

- 非同期です。 アダプターは、メッセージング エンジン スレッドのすべてのアダプターのパフォーマンスを向上できるようにをブロックしていないを[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ホスト。  

- 非トランザクションです。 アダプターはトランザクション処理された受信または送信[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]アダプター。  

- 正規表現。 アダプターは、個別のアプリケーション プロセスでは実行されません。  

- 一方向と双方向。 アダプターは、相互作用の一方向と要求-応答/送信請求-応答の両方のモードをサポートします。  

  MLLP アダプターでは、個々 のメッセージを送信したり、バッチ内のメッセージを送信することができます。 MLLP メッセージの先頭はラッパー文字、16 進数の 0x0b (とも呼ばれます、ブロックの開始または SB 文字) でマークされ、16 進数の 0x1c 文字 (ブロックの終了または EB 文字とも呼ばれます) の組み合わせによって、メッセージの末尾がマークされています。直後に 0x0d 文字 (復帰) されます。 BTAHL7 パフォーマンス カウンターは、送信メッセージに対してこれらのラッパー文字のみをカウントします。 BTAHL7 パフォーマンス カウンターでは、メッセージを受信するときにこれらのラッパーの文字はカウントされません。  

> [!NOTE]
>  SB と EB 文字を検出する機能に干渉するため、MLLP プロトコルの標準は、メッセージのペイロードで 0x20 で文字を許可されません。 変更を加える場合するこの問題に注意してください。 そのため、SB と EB 文字値を構成できます。  

 この手順では、MLLP アダプターと SOAP アダプタを構成します。  

### <a name="to-create-and-configure-the-ports"></a>作成してポートを構成するには  

1. オーケストレーション デザイナー、ドラッグ、**ポート**、ツールボックスから図形をデザイン ビュー サーフェイスの左側にあるポート画面とで水平方向に合わせて配置されるようにドロップします、 **DoorbellReceive**図形です。  

2. **ポート構成ウィザード**、 をクリックして**次**します。  

3. **ポートのプロパティ**] ページの [、**名前**フィールドに「 **SOAPReceivePort**、順にクリックします**次**します。  

4. **ポートの種類を選択します。** ページで、次の情報を入力し、順にクリックします **[次へ]** を続行します。  


   |         プロパティ          |          目的           |
   |---------------------------|-------------------------------|
   |    **ポートの種類名**     | 型**SOAPReceivePortType**します。 |
   | **通信方式** |      選択**一方向**します。      |
   |  **アクセスの制限**  | 選択**パブリック - 制限なし**します。 |


5. **ポートのバインド**] ページで [ **[次へ]** 既定値を受け入れます。  

6. **ポート ウィザードの完了**] ページで [**完了**です。  

7. ドラッグ、**ポート**、ツールボックスから図形をデザイン ビューの右側にあるポート画面とで水平方向に合わせて配置されるようにドロップします、 **DoorbellSend**図形。  

8. 使用して、**ポート構成ウィザード**手順 2 ~ 7 で行ったように、次のパラメーターを使用して、追加の送信ポートを作成します。  


   |              プロパティ               |                   パラメーター                   |
   |-------------------------------------|-----------------------------------------------|
   |      **ポートのプロパティ名**       |                 MLLPSendPort                  |
   |         **ポートの種類名**          |               MLLPSendPortType                |
   |      **通信方式**      |                    一方向                    |
   |       **アクセスの制限**       |               パブリック - 制限なし               |
   |          **ポートのバインド**           |                 後で指定します。                 |
   | **ポートの通信方向** | 常にメッセージを送信しますこのポートでします。 |


9. **オーケストレーション ビュー**  ウィンドウで、**型**、**ポートの種類**と**SOAPReceivePortType** を展開するノードを展開すると、**Operation_1**、 をクリックし、**要求**します。  

10. **プロパティ** ウィンドウのドロップダウン リストで、**メッセージの種類**、展開**スキーマ**、 をクリックし、 **BTAHL7_Project.Doorbell**.  

11. **オーケストレーション**ウィンドウで、展開**MLLPSendPortType**、展開**Operation_1**、順にクリックします**要求**します。  

12. **プロパティ** ウィンドウのドロップダウン リストで、**メッセージの種類**、展開**マルチパート メッセージの種類**、 をクリックし、 **BTAHL7_Project.DoorbellFinalMessageType**します。  

13. **名前**フィールドに「**応答**、キーを押します**Enter**します。  

14. オーケストレーション デザイン ビュー サーフェイスで、をクリックして、 **DoorbellReceive**アクション図形。  

15. **プロパティ** ウィンドウのドロップダウン リストで、**メッセージ**、 **DoorbellInputMessage**します。  

16. オーケストレーション デザイン ビュー サーフェイスで、をクリックして、 **DoorbellSend**図形。  

17. **プロパティ** ウィンドウのドロップダウン リストで、**メッセージ**、 **DoorbellFinalMessage**します。  

18. 緑色のハンドルをクリックして、 **SOAPReceivePort**の緑のハンドルにドラッグして、 **DoorbellReceive**受信図形を接続する、 **SOAPReceivePort** に**DoorbellReceive**受信図形。  

19. 緑色のハンドルをクリックして、 **DoorbellSend**図形し、上の緑色のハンドルにドラッグ、 **MLLPSendPort**接続先ポート、 **DoorbellSend** に送信図形**MLLPSendPort**ポート。  

20. をクリックして、**ソリューション エクスプ ローラー** ] タブの [オーケストレーションの種類。  

21. ソリューション エクスプ ローラーで右クリックして**BTAHL7V22Common**、 をクリックし、**ビルド**します。 成功メッセージが出力ウィンドウに表示されることを確認します。  

    > [!NOTE]
    >  成功メッセージが表示されない場合は、ソリューションのトラブルシューティングを行います。  

22. 右クリックして**BTAHL7 プロジェクト**、 をクリック**デプロイ**BTAHL7 プロジェクトを配置します。  

    続行する[手順 14。Web サービスとしてのオーケストレーションの公開](../../adapters-and-accelerators/accelerator-hl7/step-14-publish-the-orchestration-as-a-web-service.md)します。  

## <a name="see-also"></a>参照  
 [メッセージ強化のチュートリアル](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)