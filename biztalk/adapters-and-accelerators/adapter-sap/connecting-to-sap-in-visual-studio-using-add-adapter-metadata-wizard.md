---
title: "アダプター メタデータのウィザードを追加する Visual Studio を使用して SAP への接続 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a442837b-e7d8-4edb-9c5e-5603d4c58fe5
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: db24d079dc428c69733e36141280504f97728b26
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="connecting-to-sap-in-visual-studio-using-add-adapter-metadata-wizard"></a>アダプター メタデータのウィザードを追加する Visual Studio を使用して SAP への接続
[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]は BizTalk アダプターとしても公開し、そのため、使用することができます、[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]アダプターを使用して SAP システム上で実行する操作のスキーマを生成します。  
  
## <a name="connecting-to-an-sap-system-using-add-adapter-metadata-wizard"></a>接続を SAP システムを使用してアダプター メタデータのウィザードを追加  
 使用して SAP システムへの接続には、次の手順を実行、[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]です。  
  
#### <a name="to-connect-to-an-sap-system"></a>SAP システムに接続するには  
  
1.  使用して接続する、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] BizTalk ソリューションで。  
  
    1.  使用して BizTalk プロジェクトを作成[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]です。  
  
    2.  ソリューション エクスプ ローラーでプロジェクト名を右クリックし、**追加**、クリックして**生成した項目の追加**です。  
  
    3.  **生成した項目の追加** ダイアログ ボックスで、次の操作します。  
  
        |プロパティ|目的|  
        |--------------|----------------|  
        |**カテゴリ**|をクリックして**アダプターを追加**です。|  
        |**[テンプレート]**|をクリックして**アダプター メタデータの追加**です。|  
  
    4.  **[追加]**をクリックします。 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] が表示されます。  
  
    5.  アダプターの追加ウィザードで選択**WCF SAP**です。 コンピューターを選択して[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]がインストールされていると、BizTalk データベースの名前。  
  
        > [!IMPORTANT]
        >  BizTalk で構成されている WCF SAP ポートがある場合からポートを選択して、**ポート** ボックスの一覧です。  
  
    6.  **[次へ]**をクリックします。  
  
2.  **バインディングを選択**ドロップダウン リスト、選択**sapBinding**  をクリック**構成**です。  
  
3.  **アダプターの構成** ダイアログ ボックスをクリックして、**セキュリティ** タブとの間、**クライアント資格情報の種類**ドロップダウン リスト ボックスで、 **ユーザー名**ユーザー名と、SAP システムへの接続にパスワードを指定します。  
  
    > [!IMPORTANT]
    >  SAP システムへの接続に SAP セキュリティで保護されたネットワーク接続 (SNC) ライブラリを使用する場合を指定しないユーザー名とパスワード。  
  
4.  クリックして、 **URI プロパティ**タブし、接続パラメーターの値を指定します。 詳細については、接続 URI の[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を参照してください[SAP システム接続 URI を作成する](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)です。  
  
    > [!IMPORTANT]
    >  SAP システムへの接続に SAP SNC ライブラリを使用する場合は、設定、 **UseSnc**接続プロパティを**True**です。  
  
    > [!NOTE]
    >  接続パラメーターに予約済みの文字が含まれている場合、そのままを指定する必要がありますのでは、 **URI プロパティ** タブでは、エスケープ文字を使用せずします。 ただし、URI で直接指定する場合、 **URI の構成**フィールドと接続パラメーターは、予約文字を含める、適切なエスケープ文字を使用して接続パラメーターを指定する必要があります。  
  
5.  クリックして、**バインド プロパティ**タブをクリックし、対象となる操作で、必要な場合、バインド プロパティの値を指定します。 たとえば場合 ReceiveIdoc 操作の対象にする必要があります設定する、 **ReceiveIdocFormat**文字列にプロパティを連結します。 バインドのプロパティの詳細については、次を参照してください。 [mySAP Business Suite のバインドのプロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)です。  
  
    > [!NOTE]
    >  使用してメタデータを生成する場合[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]と既存の SAP WCF 送信ポートを選択して、バインドのプロパティを指定する必要はありません。 バインドのプロパティは、送信ポートの構成から取得されます。 ただし、存在する場合、デザイン時に、必要なバインドのプロパティを指定することもできます。 このような場合、メタデータの生成中にバインドのプロパティの新しい値をデザイン時に使用されます。 ただし、実行時に、バインドの送信ポートの構成のプロパティの指定値適用されます。  
  
    > [!IMPORTANT]
    >  SAP システムへの接続に SAP SNC ライブラリを使用する場合は、設定、 **SncLibrary**と**SncPartnerName**を適切な値です。  
    >   
    >  **SncLibrary**パスと SNC を使用して SAP システムに接続するために必要な Dll のファイル名は、プロパティをバインドします。 これらの Dll は、SAP クライアントを使用してコンピューター上に存在する必要がありますと[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]インストールします。 詳細については、次を参照してください。、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]インストール ガイドで使用可能な\<インストール ガイド\>: \Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Documents です。  
    >   
    >  **SncPartnerName**通信パートナーの SNC 名を取得するプロパティをバインドします。  
  
6.  **[OK]**をクリックします。  
  
7.  **[接続]**をクリックします。 接続が確立されると、接続状態は表示**接続**です。  
  
     次の図に示しています、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]接続が確立された後にすぐにします。 グラフィカル ユーザー インターフェイスが同じ、[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]です。  
  
     ![アダプター サービスの使用 ダイアログ ボックスの接続](../../adapters-and-accelerators/adapter-sap/media/00eb7c9c-3af3-4dad-8c97-2e6ae211b8f0.gif "00eb7c9c-3af3-4dad-8c97-2e6ae211b8f0")  
  
     [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] SAP システムで呼び出すことのできる各種の成果物を含む別のノードが表示されます。 たとえば、 **RFC**ノードに接続されている SAP システムで使用できるすべての Rfc に含まれます。 これらのノードに関する詳細については、次を参照してください。[メタデータのノード Id](../../adapters-and-accelerators/adapter-sap/metadata-node-ids4.md)です。  
  
## <a name="see-also"></a>参照  
 [Visual Studio で SAP システムに接続する](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md)