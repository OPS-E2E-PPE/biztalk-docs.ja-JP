---
title: エンコードのサポートを拡張 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 93a40fa6-d0da-416e-97fb-675ddde3f005
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 41275124cdf0db7329751c5973bbde0685bd49ec
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65255298"
---
# <a name="extended-encoding-support"></a>エンコードのサポートを拡張
既定では HL7 受信のみ BTAHL72X、パイプラインでは ASCII エンコーディングがサポートされます。 つまり、値 127 の置き換えよりも大きいと、入力メッセージの任意の文字"?"。 これは、127 より大きい値と文字は、ASCII 文字セットでは表されないためです。  
  
 [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] 新しい 2 つのエンコーディングをサポートをします。  
  
- 西ヨーロッパ言語  
  
- UTF-8  
  
  作成して拡張エンコードのサポートを実装するカスタム パイプライン コンポーネントをビルドします。 カスタム パイプライン コンポーネントは、BTAHL7 2.X 逆アセンブラーです。 メッセージを処理するカスタム パイプラインを使用する受信場所を作成します。 カスタム パイプラインと受信場所をテストするには、BTAHL7 2.XSendPipeline を使用する送信ポートを作成します。  
  
### <a name="to-create-a-custom-pipeline"></a>カスタム パイプラインを作成するには  
  
1. [!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)]、新しい追加**空の BizTalk Server プロジェクト**します。  
  
2. ソリューション エクスプ ローラーで新しいプロジェクトを右クリックし、をクリックして**追加**、 をクリックし、**新しい項目の**します。  
  
3. **新しい項目の追加** ダイアログ ボックスで、新しい追加**受信パイプライン**します。  
  
4. パイプラインのツールボックスからドラッグ、 **BTAHL7 2.X 逆アセンブラー**パイプライン エディターにドロップ、**逆アセンブル**ステージ**ここにドロップ**ターゲット。  
  
   > [!NOTE]
   >  BTAHL7 2.7 逆アセンブラーがツールボックスにない場合は、ツールボックスで、右クリックし、クリックして**アイテムの選択**します。 **ツールボックス アイテムの選択** ダイアログ ボックスで、 **BizTalk パイプライン コンポーネント** タブで、、 **BTAHL7 2.X 逆アセンブラー**チェック ボックスをオンにし**ok**.  
  
5. [プロパティ] ウィンドウで、 **BTAHL7 2.X 逆アセンブラー**から、**エンコード charset**ドロップダウン リストで、**西ヨーロッパ言語**または**UTF8**エンコードします。  
  
   > [!NOTE]
   >  HL7 には、ASCII (既定)、西ヨーロッパ言語、および UTF8 エンコードのみサポートしています。 HL7 をサポートしていないため、他のエンコード オプションを選択しません。  
  
6. **[ファイル]** メニューの **[すべてを保存]** をクリックします。  
  
7. プロジェクトをデプロイします。  
  
    新しい受信場所で続行します。  
  
### <a name="to-create-a-receive-location-that-uses-the-custom-pipeline"></a>カスタム パイプラインを使用する受信場所を作成するには  
  
1. **開始** メニューのをクリックして**プログラム**、 をポイント[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]、 をクリックし、 **BizTalk Server 管理**。  
  
2. BizTalk Server 管理コンソールで [ [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] **管理**、展開**BizTalk グループ**、展開**アプリケーション**アプリケーションの展開パイプライン アセンブリの指定した (既定では、 **BizTalk アプリケーション 1**)、右クリックして**受信場所**、] をポイント**新規**、順にクリックします**一方向の受信場所**します。  
  
3. **受信場所のプロパティ** ダイアログ ボックスで、**受信パイプライン**-ドロップダウン リストで、作成したパイプラインのカスタムの名前を選択します。 (これは、BTAHL7 ではない、カスタムのパイプライン オブジェクトの名前をパイプラインの 2 倍にします)。  
  
### <a name="to-create-a-send-port-to-test-the-receive-location-and-pipeline"></a>受信場所とパイプラインをテストする送信ポートを作成するには  
  
1. **開始** メニューのをクリックして**プログラム**、 をポイント[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]、 をクリックし、 **BizTalk Server 管理**。  
  
2. BizTalk Server 管理コンソールで [ [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] **管理**、展開**BizTalk グループ**、展開**アプリケーション**アプリケーションの展開パイプライン アセンブリの指定した (既定では、 **BizTalk アプリケーション 1**)、右クリック**送信ポート**、] をポイント**新規**順にクリックします**静的な一方向送信ポート**します。  
  
3. **送信ポートのプロパティ** ダイアログ ボックスで、**送信パイプライン**ドロップダウン リストで、 **BTAHL72XSendPipeline**します。  
  
### <a name="to-test-the-receive-location-and-pipeline"></a>受信場所とパイプラインをテストするには  
  
-   特殊文字を含むカスタム パイプラインで受信場所で指定されている場所に指定した同じエンコードで保存されたファイルを削除します。 出力場所にファイルには、特殊文字を保持する必要があります。  
  
    > [!NOTE]
    >  サポートされているエンコードを使用するファイルを処理しようとしたかどうか (のみ ASCII、西ヨーロッパ言語、および UTF8 がサポートされていることに注意してください)、エラーの ID を持つアプリケーション イベント ビューアーでエラーが記録されます。5633.  
  
    > [!NOTE]
    >  UTF8 エンコード用に構成されたカスタム パイプラインをテストする場合は、バイト オーダー マーク (BOM) 文字をメソッドに渡すメッセージに添付する必要があります。 西ヨーロッパのエンコード用に構成されたカスタム パイプラインをテストする場合は、BOM 文字をアタッチできません。