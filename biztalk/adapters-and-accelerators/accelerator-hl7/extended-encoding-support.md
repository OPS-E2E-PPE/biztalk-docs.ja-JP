---
title: "エンコードのサポートを拡張 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 93a40fa6-d0da-416e-97fb-675ddde3f005
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9e36c3baff4ac33f2878295791bb3f6615c1b25d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="extended-encoding-support"></a>エンコードのサポートを拡張
既定で、HL7 の受信パイプライン、BTAHL72X がのみ ASCII エンコードをサポートします。 つまり、この値に置き換え、127 より大きいと、入力メッセージの任意の文字"?"。 これは、127 より大きい値を等価の値を持つ文字は、ASCII 文字セットで表されないためです。  
  
 [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]2 つの新しいエンコードをサポートをします。  
  
-   西ヨーロッパ言語  
  
-   UTF-8  
  
 作成して拡張エンコードのサポートを実装するカスタム パイプライン コンポーネントをビルドします。 カスタム パイプライン コンポーネントは、BTAHL7 2.X 逆アセンブラーです。 メッセージを処理するカスタム パイプラインを使用する受信場所を作成します。 カスタム パイプラインと受信場所をテストするには、BTAHL7 2.XSendPipeline を使用する送信ポートを作成します。  
  
### <a name="to-create-a-custom-pipeline"></a>カスタム パイプラインを作成するには  
  
1.  [!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)]、追加、新しい**空の BizTalk Server プロジェクト**です。  
  
2.  ソリューション エクスプ ローラーで、新しいプロジェクトを右クリックし、をクリックして**追加**、クリックして**新しい項目の**します。  
  
3.  **新しい項目の追加** ダイアログ ボックスで、追加、新しい**受信パイプライン**です。  
  
4.  パイプライン ツールボックスからドラッグ、 **BTAHL7 2.X 逆アセンブラー**パイプライン エディタを上にドロップし、**逆アセンブル**ステージ**ここにドロップ**ターゲットです。  
  
    > [!NOTE]
    >  BTAHL7 2.7 逆アセンブラーでない場合、ツールボックスのツールボックスを右クリックし、をクリックして**アイテムの選択**です。 **ツールボックス アイテムの選択** ダイアログ ボックスで、 **BizTalk パイプライン コンポーネント** タブで、、 **BTAHL7 2.X 逆アセンブラー**チェック ボックスをクリックして**ok**.  
  
5.  [プロパティ] ウィンドウで、 **BTAHL7 2.X 逆アセンブラー**から、**エンコード charset**ドロップダウン リストで、**西ヨーロッパ言語**または**UTF8**エンコードします。  
  
    > [!NOTE]
    >  HL7 には、ASCII (既定)、西ヨーロッパ言語、および UTF8 エンコードのみサポートしています。 HL7 はそれらをサポートしないため、他のエンコード オプションを選択しません。  
  
6.  **[ファイル]** メニューの **[すべてを保存]**をクリックします。  
  
7.  プロジェクトを配置する。  
  
     新しい受信場所で続行します。  
  
### <a name="to-create-a-receive-location-that-uses-the-custom-pipeline"></a>カスタム パイプラインを使用する受信場所を作成するには  
  
1.  **開始** メニューのをクリックして**プログラム**、をポイント[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]、クリックして**BizTalk Server 管理コンソール**です。  
  
2.  BizTalk Server 管理コンソールで、展開[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]**管理**、展開**BizTalk グループ**、展開**アプリケーション**アプリケーションの展開パイプライン アセンブリ用に指定した (既定では、 **BizTalk アプリケーション 1**) を右クリックして**受信場所**、をポイント**新規**をクリックし、**一方向の受信場所**です。  
  
3.  **受信場所のプロパティ** ダイアログ ボックスで、**受信パイプライン**ドロップダウン リストで、作成したパイプラインのカスタムの名前を選択します。 (これは、名前のカスタム パイプライン オブジェクト、BTAHL7 ではないのパイプラインの 2 倍にします)。  
  
### <a name="to-create-a-send-port-to-test-the-receive-location-and-pipeline"></a>受信場所およびパイプラインをテストする送信ポートを作成するには  
  
1.  **開始** メニューのをクリックして**プログラム**、をポイント[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]、クリックして**BizTalk Server 管理コンソール**です。  
  
2.  BizTalk Server 管理コンソールで、展開[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]**管理**、展開**BizTalk グループ**、展開**アプリケーション**アプリケーションの展開パイプライン アセンブリの指定 (既定では、 **BizTalk アプリケーション 1**) を右クリックして**送信ポート**、をポイント**新規**をクリックして**静的な一方向送信ポート**です。  
  
3.  **送信ポートのプロパティ** ダイアログ ボックスで、**送信パイプライン**ドロップダウン リストで、 **BTAHL72XSendPipeline**です。  
  
### <a name="to-test-the-receive-location-and-pipeline"></a>受信場所およびパイプラインをテストするには  
  
-   特殊文字を含む、カスタム パイプラインで受信場所で指定された場所に指定した同じエンコードで保存したファイルを削除します。 出力場所にファイルには、特殊文字を保持する必要があります。  
  
    > [!NOTE]
    >  サポートされているエンコードを使用するファイルを処理しようとする場合 (のみ ASCII、西ヨーロッパ言語、および UTF8 がサポートされていることに注意してください) エラーの ID を持つアプリケーション イベント ビューアーにエラーが記録: 5633 です。  
  
    > [!NOTE]
    >  UTF8 エンコーディング用に構成されたカスタム パイプラインをテストする場合は、メソッドに渡すメッセージをバイト オーダー マーク (BOM) 文字をアタッチする必要があります。 西ヨーロッパ言語エンコード用に構成されたカスタム パイプラインをテストする場合は、BOM 文字をアタッチできません。