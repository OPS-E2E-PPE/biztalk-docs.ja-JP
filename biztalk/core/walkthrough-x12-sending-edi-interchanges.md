---
title: チュートリアル (X12):EDI インターチェンジの送信 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 05533821-b9eb-44bc-af65-b6fb0b545137
caps.latest.revision: 36
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 50db444708b4960f1e3e12236b3f3006fd2567e0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65246469"
---
# <a name="walkthrough-x12-sending-edi-interchanges"></a>チュートリアル (X12):EDI インターチェンジの送信
このチュートリアルでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を使用して EDI インターチェンジの送信用のソリューションを作成する一連の手順について説明します。  

## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  

## <a name="how-the-solution-sends-edi-interchanges"></a>ソリューションにより EDI インターチェンジを送信する方法  
 このソリューションは次の処理を実行します。  

1.  一方向の FILE 受信ポートは、Fabrikam から EDI メッセージを受信します。  

2.  EdiReceive パイプラインを使用して、受信ポートはメッセージをチェックし、XML に変換します。 次に、受信ポートはテスト メッセージをメッセージ ボックスにドロップします。  

3.  静的な一方向の送信ポートが、メッセージ ボックスから XML メッセージを取得します。  

4.  静的な一方向の送信ポートは、メッセージ スキーマと照合し、EDI メッセージを検証して、EDI メッセージを EDI インターチェンジにシリアル化した後、EDI メッセージを取引先である Contoso のローカル フォルダーに送信します。  

## <a name="the-functionality-in-this-solution"></a>このソリューションの機能  
 このチュートリアルでは、以下の機能を使用します。  

- このチュートリアルでは、受信確認の受信はテストされません。 受信確認を受信する方法については、「実証[チュートリアル (X12):EDI インターチェンジの受信と受信確認の送信](../core/walkthrough-x12--receive-edi-interchanges-and-send-back-an-acknowledgement.md)  

- このソリューションは、EDIFACT エンコードではなく X12 エンコードを使用するインターチェンジを対象に設計されています。  

  > [!NOTE]
  >  HIPAA および EDIFACT エンコードに使用される構成は、X12 エンコードに使用される構成によく似ています。  

- EDI の種類の検証および拡張された検証は、送信インターチェンジに対して実行されます。  

- このソリューションでは、トランスポートの種類が FILE である静的な一方向の送信ポートが使用されます。  

  > [!NOTE]
  >  静的な一方向の送信ポートの代わりに、静的な双方向の送信ポートを使用して、インターチェンジの送信および受信確認の受信を行うこともできます。 また、動的な一方向の送信ポートを使用してインターチェンジを送信することもできます。 動的送信ポートの使用に関する詳細については、次を参照してください。 [EDI インターチェンジの送信と受信確認を動的送信ポートを構成する](../core/configuring-a-dynamic-send-port-to-send-edi-interchanges-and-acknowledgments.md)します。  

  > [!NOTE]
  >  HTTP アダプターと AS2 トランスポートを使用できます。 その方法の詳細については、次を参照してください。[チュートリアル (AS2)。同期 MDN による AS2 経由での EDI の送信](../core/walkthrough-as2-sending-edi-over-as2-with-a-synchronous-mdn.md)または[チュートリアル (AS2)。非同期 MDN による AS2 経由での EDI の送信](../core/walkthrough-as2-sending-edi-over-as2-with-an-asynchronous-mdn.md)します。  

- EDI レポートが有効になり、インターチェンジの状態レポートに表示するトランザクション セットが保存されます。  

- テスト目的の場合、このソリューションではテスト メッセージの受信に受信場所が使用されます。  

  次の図は、静的な一方向の送信ポートを使用するこのソリューションのアーキテクチャを示しています。  

  ![EDI インターチェンジの送信](../core/media/6915024c-687c-4076-a730-3f7b9d2db7fb.gif "6915024c-687c-4076-a730-3f7b9d2db7fb")  

## <a name="configuring-and-testing-the-walkthrough"></a>チュートリアルの構成とテスト  
 このソリューションに必要な手順は以下のとおりです。  

- BizTalk プロジェクトに必要なメッセージ スキーマを追加してビルドおよび展開し、送信インターチェンジを [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で処理するときにそのスキーマを利用できるようにします。  

- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が EDI インターチェンジを受信するための受信ポートと受信場所を作成します。 この受信場所は、Fabrikam が Contoso に送信する EDI インターチェンジをドロップするファイル フォルダーに関連付けられています。 受信場所では EdiReceive 受信パイプラインを使用します。  

- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が EDI インターチェンジを Contoso に送信するための送信ポートを作成します。 このチュートリアルでは、静的な一方向の送信ポートを作成します。  

- Fabrikam および Contoso の両方にパーティ (取引先) を作成します。  

- 両方の取引先それぞれにビジネス プロファイルを作成します。  

- 受信するメッセージの EDI プロパティを構成して、2 つのプロファイル間のアグリーメントを作成します。  

- テスト EDI インターチェンジを使用して、このチュートリアルをテストします。  

  > [!NOTE]
  >  テスト メッセージには、EDI インターフェイス開発チュートリアルで使用した SamplePO.txt ファイルを使用できます。 このファイルは、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\ フォルダーにあります。 これは、X12 850 メッセージです。  

### <a name="configuring-the-walkthrough"></a>チュートリアルの構成  
 ここでは、チュートリアルを構成する手順について説明します。  

##### <a name="to-deploy-the-message-schema"></a>メッセージ スキーマを展開するには  

1. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で、BizTalk プロジェクトを作成するか、開きます。  

   > [!NOTE]
   >  このトピックは、EDI スキーマ、パイプライン、およびオーケストレーションを含む BizTalk EDI アプリケーションに別のアプリケーションから参照を既に追加していることを前提としています。 そうでない場合は、次を参照してください。 [、BizTalk Server EDI アプリケーションへの参照を追加する方法](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782)します。  

2. プロジェクトを右クリックし、[**追加**、] をクリックし、**既存項目の**します。 スキーマが [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI にあるフォルダーに移動し、スキーマをダブルクリックします。  

   > [!NOTE]
   >  EDI スキーマが \XSD_Schema\EDI フォルダーに展開されていないが、実行、 **MicrosoftEdiXSDTemplates.exe** \XSD_Schema\EDI フォルダーにスキーマを既定のフォルダーに解凍内のファイル。  
   > 
   > [!NOTE]
   >  EDI インターフェイス開発チュートリアルで使用した SamplePO.txt ファイルを使用する場合は、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\Inbound_EDI フォルダーにある X12_00401_850.xsd スキーマを使用する必要があります。 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema フォルダーにある X12 850 スキーマは使用しないでください。  

3. アセンブリ キー ファイルをプロジェクトに追加し、アセンブリをビルドして展開します。  

##### <a name="to-create-a-one-way-receive-port-for-fabrikam-to-receive-the-edi-interchange"></a>EDI インターチェンジを受信するための一方向の受信ポート (Fabrikam 用) を作成するには  

1. Windows エクスプ ローラーで、インターチェンジを受信するローカル フォルダーを作成します。  

2. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックし、**受信ポート**ノードの下、 **BizTalk アプリケーション 1**に**新規**をクリックして**一方向受信ポート**します。  

3. 受信ポートの名前を指定し、をクリックし、**受信場所**コンソール ツリーでします。  

4. **[新規]** をクリックします。  

5. [受信場所の名前**ファイル**の**型**、] をクリックし、**構成**。  

6. フォルダを**受信フォルダー**、入力と **\*.txt**ファイル マスク。  

7. **[OK]** をクリックします。  

8. **受信パイプライン**、 **EdiReceive**します。  

9. をクリックして**OK**、順にクリックします**OK**もう一度です。  

10. コンソール ツリーで、クリックして**受信場所**します。 **受信場所**ウィンドウを右クリックし、受信場所をクリックして**を有効にする**します。  

##### <a name="to-create-a-static-one-way-send-port-for-contoso-to-send-the-edi-interchange"></a>EDI インターチェンジを送信するための静的な一方向の送信ポート (Contoso 用) を作成するには  

1. Windows エクスプローラーで、EDI インターチェンジを送信する先のローカル フォルダーを作成します。  

2. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックし、**送信ポート**ノードの下、 **BizTalk アプリケーション 1**に**新規**をクリックして**静的な一方向送信ポート**します。  

3. **送信ポートのプロパティ**ダイアログ ボックスで、送信ポートの名前。  

4. **トランスポート**セクションで、**型**、たとえば、**ファイル**します。  

5. ファイルの種類を使用して、場合**構成**します。 **先フォルダー**インターチェンジを送信するフォルダーを参照します。 **ファイル名**、入力 **%MessageID%.edi**します。 **[OK]** をクリックします。  

6. **送信パイプライン**、 **EdiSend**します。  

7. コンソール ツリーで、選択**フィルター**を使用して、メッセージをサブスクライブする送信ポートのフィルター式を入力します。 たとえば、元のテスト メッセージを受信する受信場所をフィルター式として使用できます。 **プロパティ**、入力**BTS します。ReceivePortName**; の**演算子**、入力**==**; と**値**に作成した受信ポートの名前を入力します。Fabrikam から XML メッセージを受信します。  

   > [!NOTE]
   >  フィルター処理の対象には、別の任意のプロパティ (たとえば BTS.MessageType) を指定することもできます。  

8. **[OK]** をクリックします。  

9. をクリックして、**送信ポート**、管理コンソール内のノードは、送信ポートを右クリックし をクリックし、**開始**。  

##### <a name="to-create-a-party-and-a-business-profile-for-fabrikam"></a>Fabrikam のパーティとビジネス プロファイルを作成するには  

1. 右クリックし、**パーティ**内のノード、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、 をポイント**新規**、 をクリックし、**パーティ**します。  

2. パーティの名前を入力、**名前**テキスト ボックス、およびクリック **[ok]** します。  

   > [!NOTE]
   >  選択して、**ローカル BizTalk 受信パーティまたはサポートがこのパーティからメッセージを送信したメッセージを処理**チェック ボックスをオンをホストしている同じ組織のパーティの作成中であること指定できる[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. その指定に基づいて、アグリーメントを作成するときに一部のプロパティが有効または無効になります。 ただし、このチュートリアルでは、このチェック ボックスはオンのままでかまいません。  

3. パーティ名を右クリックし、[**新規**、] をクリックし、**ビジネス プロファイル**します。  

4. **プロファイル プロパティ**] ダイアログ ボックスの [、**全般**ページで、入力 **[fabrikam_profile]** で、**名前**テキスト ボックス。  

   > [!NOTE]
   >  パーティを作成すると、プロファイルも作成されます。 新しいプロファイルを作成する代わりに、そのプロファイルの名前を変更して使用できます。 プロファイルの名前を変更するには、プロファイルを右クリックして**プロパティ**します。 **全般** ページで、プロファイルの名前を指定します。  

##### <a name="to-create-a-party-and-a-business-profile-for-contoso"></a>Contoso のパーティとビジネス プロファイルを作成するには  

1. 右クリックし、**パーティ**内のノード、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、 をポイント**新規**、 をクリックし、**パーティ**します。  

2. パーティの名前を入力、**名前**テキスト ボックス、およびクリック **[ok]** します。  

   > [!NOTE]
   >  選択して、**ローカル BizTalk 受信パーティまたはサポートがこのパーティからメッセージを送信したメッセージを処理**チェック ボックスをオンをホストしている同じ組織のパーティの作成中であること指定できる[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. その指定に基づいて、アグリーメントを作成するときに一部のプロパティが有効または無効になります。 ただし、このチュートリアルでは、このチェック ボックスはオンのままでかまいません。  

3. パーティ名を右クリックし、[**新規**、] をクリックし、**ビジネス プロファイル**します。  

4. **プロファイル プロパティ**] ダイアログ ボックスの [、**全般**ページで、入力**Contoso_Profile**で、**名前**テキスト ボックス。  

   > [!NOTE]
   >  パーティを作成すると、プロファイルも作成されます。 新しいプロファイルを作成する代わりに、そのプロファイルの名前を変更して使用できます。 プロファイルの名前を変更するには、プロファイルを右クリックして**プロパティ**します。 **全般** ページで、プロファイルの名前を指定します。  

##### <a name="to-create-an-agreement-between-the-two-business-profiles"></a>2 つのビジネス プロファイル間のアグリーメントを作成するには  

1. 右クリック**fabrikam_profile**、 をポイント**新規**、 をクリックし、**契約**します。  

2. **全般プロパティ** ページの**名前**テキスト ボックスに、アグリーメントの名前を入力します。  

3. **プロトコル**ドロップダウン リストで、 **X12**します。  

4. **2 番目のパートナー**セクションから、**名前**ドロップダウン リストで、 **Contoso**します。  

5. **2 番目のパートナー**セクションから、**プロファイル**ドロップダウン リストで、 **Contoso_Profile**します。  

    2 つの新しいタブが横に追加の取得と表示されます、**全般**タブ。各タブに 1 つの一方向のアグリーメントを構成するようになっており、一方向の各アグリーメントが 1 つの完全なメッセージ トランザクション (メッセージの送信と受信確認の送信を含む) を表します。  

6. **全般** タブで、**全般プロパティ**ページで、**共通のホスト設定**セクションで、**レポートをオン**、し、選択**メッセージ ペイロードを格納するレポートの**します。  

7. 次のタスクを実行、 **Fabrikam が Contoso を ->** タブ。  

   1. **識別子**ページで、**インターチェンジの設定**セクションで、修飾子と識別子のフィールドの値を入力 (**ISA5**、 **ISA6**、 **ISA7**、および**ISA8**) テスト メッセージのヘッダー フィールドの値に対応しています。  

      > [!NOTE]
      >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、アグリーメントの解決を実行するために、送信者と受信者の修飾子フィールドおよび ID フィールドを必ず指定する必要があります。 値と一致します**ISA5**、 **ISA6**、 **ISA7**、および**ISA8**をアグリーメントのプロパティと、インターチェンジ ヘッダー。 また、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、送信者の修飾子および識別子を照合して (受信者の修飾子および識別子は不要)、アグリーメントを解決します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、アグリーメントを解決できない場合、フォールバック アグリーメントのプロパティが使用されます。  
      > 
      > [!NOTE]
      >  テスト メッセージとして「EDI インターフェイス開発チュートリアル」の SamplePO.txt ファイルを使用する場合は、設定**ISA5**に**ZZ**、 **ISA6**に**THEM**、 **ISA7**に**ZZ**、および**ISA8**に**米国**します。  

   2. **検証**ページで、**インターチェンジの設定**セクションをご確認ください**重複している isa13 を確認**オプションが選択されていません。  

      > [!NOTE]
      >  オフにすると、**重複している isa13 を確認**プロパティでは、同じメッセージの複数のインスタンスを受信することができます。  

   3. **文字セットと区切り記号**ページで、**インターチェンジの設定**セクションで、 **CR LF**オプション。  

   4. **送信ポート**ページで、**インターチェンジの設定**セクションで、Fabrikam から EDI インターチェンジを受信する送信ポートを関連付けます。 **送信ポート**グリッドで、**名前**列が空のセルをクリックし、ボックスの一覧から、Fabrikam から EDI インターチェンジを受信するために作成した送信ポートを選択します。 します。  

   5. **検証**ページで、**トランザクション セットの設定**セクションで、そのまま使用**EDI 型の検証**に、チェック**拡張された検証**.  

   6. 使用するかどうかに付属する標準スキーマのいずれかの[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]の**ローカル ホスト設定**ページで、**トランザクション セットの設定**セクションでを使用するスキーマの名前空間を選択します。受信インターチェンジを処理します。  


      |       プロパティ       |                           目的                            |
      |----------------------|-----------------------------------------------------------------|
      |     **[Default]**      |                列のチェック ボックスをオンにします                |
      |     **St1 の場合**      |                選択**850 - 注文書**します。                 |
      |       **[GS2]**        |                         入力**THEM**します。                         |
      | **Target Namespace** | 選択 **<http://schemas.microsoft.com/BizTalk/EDI/X12/2006>** します。 |

      > [!NOTE]
      >  プロパティを設定すると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、受信 850 インターチェンジの処理に使用するスキーマを決定できるようになります。 グリッド内の行に入力された [GS02] と [ST01] の値がインターチェンジに設定されている場合は、同じ行にあるターゲットの名前空間により、使用するスキーマが決定されます。  

   7. **エンベロープ**ページで、**トランザクション セットの設定**セクションで、グリッドの最初の行のすべての列の値を入力します。  


      |       プロパティ       |                                                                                                                                               目的                                                                                                                                               |
      |----------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
      |     **[Default]**      | チェック ボックスをオン、**既定**列。 **注:** 既定の値としてこの行を選択すると**GS1**、 **GS2**、 **GS3**、 **GS7**、および**GS8**は使用されている場合であってもの値は、**トランザクションの種類**、**バージョン/リリース**と**ターゲットの名前空間**と一致するメッセージではありません。 |
      | **トランザクションの種類** |                                                                                                                テスト メッセージのメッセージの種類を選択します。 **850 - 注文書**します。                                                                                                                 |
      | **バージョン/リリース**  |                                                                                                                                   EDI のバージョンを入力**00401**します。                                                                                                                                    |
      | **ターゲットの名前空間** |                                                                                                                    選択 **<http://schemas.microsoft.com/BizTalk/Edi/X12/2006>** します。                                                                                                                     |
      |       **[GS1]**        |                                                                                                      テスト メッセージのメッセージの種類が選択されていることを確認**PO - 注文書 (850)** します。                                                                                                      |
      |       **[GS2]**        |                                                                                                                               アプリケーション送信者を表す値を入力します。                                                                                                                                |
      |       **[GS3]**        |                                                                                                                              アプリケーション受信者を表す値を入力します。                                                                                                                               |
      |       **GS4**        |            日付の形式を選択します。 **注:** ドロップダウン リストで、値を選択し、だけでなく、既定値を表示するフィールドをクリックする必要があります。 ドロップダウン リストから値を選択せずにフィールドをクリックしても、値は実際に選択されません。            |
      |       **GS5**        |                                                                                                                                 時刻の形式を選択します。                                                                                                                                  |
      |       **GS7**        |                                                                                                                           選択**X - 正式認可を受けた Standards Committee X12**します。                                                                                                                           |
      |       **GS8**        |                                                                                                                        EDI のバージョンが入力されていることを確認**00401**します。                                                                                                                        |

      > [!NOTE]
      >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] GS01、GS02、GS03、GS04、GS05、GS07、および入力した値に基づいて、送信する受信確認の GS08 の値が設定されます**トランザクション タイプ**、**バージョン/リリース**、および**ターゲット名前空間**します。 送信パイプラインは、トランザクション セットの種類、X12 バージョン、およびターゲットの名前空間と、メッセージ ヘッダー内の対応する値との照合を試みます。 成功すると、その値が使用 GS に関連付けられている、**トランザクションの種類**、**バージョン/リリース**、および**ターゲットの名前空間**値。  

8. 次のタスクを実行、 **Contoso が Fabrikam]-> [** タブ。  

   > [!NOTE]
   >  このチュートリアルでは、必要な値をタブに指定し、アグリーメントを正常に作成できるようにします。 アグリーメントを正常に作成する両方の一方向アグリーメント タブの値に対して定義されている必要があります**ISA5**、 **ISA6**、 **ISA7**、および**ISA8**します。  

   1.  **識別子**ページで、**インターチェンジの設定**セクションで、修飾子と識別子のフィールドの値を入力 (**ISA5**、 **ISA6**、 **ISA7**、および**ISA8**) テスト メッセージのヘッダー フィールドの値に対応しています。  

       > [!NOTE]
       >  テスト メッセージとして「EDI インターフェイス開発チュートリアル」の SamplePO.txt ファイルを使用する場合は、設定**ISA5**に**ZZ**、 **ISA6**に**米国**、 **ISA7**に**ZZ**、および**ISA8**に**THEM**します。  

9. **[適用]** をクリックします。  

10. **[OK]** をクリックします。 新しく追加したアグリーメントが一覧表示、**契約**のセクション、**パーティとビジネス プロファイル**ウィンドウ。 新しく追加したアグリーメントは既定で有効になります。  

### <a name="testing-the-walkthrough"></a>チュートリアルのテスト  
 ここでは、チュートリアルをテストする方法について説明します。  

##### <a name="to-test-the-walkthrough"></a>チュートリアルをテストするには  

1. Windows エクスプローラーで、テスト EDI インターチェンジをローカル受信フォルダーにドロップします。  

   > [!NOTE]
   >  テスト メッセージには、EDI インターフェイス開発チュートリアルで使用した SamplePO.txt ファイルを使用できます。 このファイルは、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial フォルダーにあります。 これは、X12 850 メッセージです。 このメッセージを使用する場合は、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\Inbound_EDI フォルダーにある X12_00401_850.xsd スキーマを展開しておく必要があります。 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema フォルダーにある X12 850 スキーマは使用しないでください。  

2. Windows エクスプローラーで、送信ポートに指定した送信先のフォルダーを開きます。 アグリーメントのプロパティに入力した値と一致する ISA、GS、および ST ヘッダーを保持する出力 EDI インターチェンジがフォルダーに含まれていることを確認します。  

## <a name="see-also"></a>参照  
 [BizTalk Server EDI ソリューションの開発と構成](../core/developing-and-configuring-biztalk-server-edi-solutions.md)