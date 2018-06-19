---
title: ビジュアルの Siebel システムへの接続 Studio を使用して、アダプター メタデータのウィザードを追加 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e0a82fcc-b3ac-4936-9210-03c99d3741d7
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e9fc38299ffdce6cf6227cacb7de0cae84b22091
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222770"
---
# <a name="connect-to-the-siebel-system-in-visual-studio-using-add-adapter-metadata-wizard"></a>ビジュアルの Siebel システムへの接続 Studio を使用して、アダプター メタデータのウィザードを追加
[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]は BizTalk アダプターとしても公開し、そのため、使用することができます、[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]アダプターを使用して、Siebel システムに対して実行する操作のスキーマを生成します。  
  
## <a name="connecting-to-a-siebel-system-using-add-adapter-metadata-wizard"></a>アダプター メタデータのウィザードの追加を使用する Siebel システムへの接続  
 使用して Siebel システムへの接続には、次の手順を実行、[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]です。  
  
#### <a name="to-connect-to-a-siebel-system"></a>Siebel システムに接続するには  
  
1.  使用して接続する、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] BizTalk ソリューションで。  
  
    1.  使用して BizTalk プロジェクトを作成[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]です。  
  
    2.  ソリューション エクスプ ローラーでプロジェクトを右クリックし、**追加**、クリックして**生成した項目の追加**です。  
  
    3.  **生成した項目の追加** ダイアログ ボックスで、次の操作します。  
  
        |プロパティ|目的|  
        |--------------|----------------|  
        |**カテゴリ**|をクリックして**アダプター サービスの使用**です。|  
        |**[テンプレート]**|をクリックして**アダプター サービスの使用**です。|  
  
    4.  **[追加]** をクリックします。 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] が表示されます。  
  
    5.  [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、WCF Siebel を選択します。 コンピューターを選択して[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]がインストールされていると、BizTalk データベースの名前。  
  
        > [!IMPORTANT]
        >  既に存在する場合、 **Wcf-siebel**で構成されている BizTalk のポートからポートを選択して、**ポート** ボックスの一覧です。  
  
    6.  **[次へ]** をクリックします。  
  
2.  **バインディングを選択**ドロップダウン リスト、選択**siebelBinding**、クリックして**構成**です。  
  
3.  **アダプターの構成** ダイアログ ボックスをクリックして、**セキュリティ** タブとの間、**クライアント資格情報の種類**ドロップダウン リスト ボックスで、 **ユーザー名**.  
  
4.  ユーザー名と Siebel システムへの接続にパスワードを指定します。  
  
5.  クリックして、 **URI プロパティ**タブをクリックし、接続パラメーターの値を指定します。 詳細については、接続 URI の[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]を参照してください[Siebel システム接続 URI を作成](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md)です。  
  
    > [!NOTE]
    >  接続パラメーターに予約済みの文字が含まれている場合、そのままを指定する必要がありますのでは、 **URI プロパティ** タブでは、エスケープ文字を使用せずします。 ただし、URI で直接指定する場合、 **URI の構成**フィールドと接続パラメーターは、予約文字を含める、適切なエスケープ文字を使用して接続パラメーターを指定する必要があります。  
  
6.  クリックして、**バインド プロパティ**タブをクリックし、対象となる操作で、必要な場合、バインド プロパティの値を指定します。 バインドのプロパティの詳細については、次を参照してください。 [BizTalk Adapter for Siebel のバインド プロパティ読む](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md)です。  
  
    > [!NOTE]
    >  使用してメタデータを生成する場合[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]と既存の WCF Siebel 送信ポートを選択して、バインドのプロパティを指定する必要はありません。 バインドのプロパティは、送信ポートの構成から取得されます。 ただし、存在する場合、デザイン時に、必要なバインドのプロパティを指定することもできます。 このような場合、メタデータの生成中にバインドのプロパティの新しい値をデザイン時に使用されます。 ただし、実行時に、バインドの送信ポートの構成のプロパティの指定値適用されます。  
  
7.  **[OK]** をクリックします。  
  
8.  **[接続]** をクリックします。 接続が確立されると、接続状態は表示**接続**です。  
  
     次の図に示しています、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]接続が確立された後にすぐにします。  
  
     ![アダプター サービスの使用 ダイアログ ボックスの接続](../../adapters-and-accelerators/adapter-siebel/media/siebel-adpt-lesson1-step3-01-connected.gif "SIEBEL-ADPT-Lesson1-Step3-01-connected")  
  
     [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] Siebel システムで実行できるさまざまな操作を含む別のノードが表示されます。 たとえば、**ビジネス オブジェクト**ノードには、すべてのビジネス オブジェクトと Siebel システムで呼び出すことができるビジネス コンポーネントが含まれています。 同様に、**ビジネス サービス**ノードには、すべてのビジネス サービスに接続されている Siebel システムが含まれています。 これらのノードに関する詳細については、次を参照してください。[メタデータのノード Id](../../adapters-and-accelerators/adapter-siebel/metadata-node-ids1.md)です。