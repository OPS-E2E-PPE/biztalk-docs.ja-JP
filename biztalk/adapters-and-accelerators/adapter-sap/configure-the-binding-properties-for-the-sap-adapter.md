---
title: "SAP アダプターのバインドのプロパティを構成する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- binding properties, specifying at design time
- binding properties, specifying at run time
ms.assetid: 259a5895-c19d-409c-b2fc-bfdf59d5d74b
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a16a95818ed4d63fd97b9fca1f9ea86ebd14de80
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configure-the-binding-properties-for-the-sap-adapter"></a>SAP アダプターのバインドのプロパティを構成します。
[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]動作特性を制御できるようにするいくつかのバインドのプロパティを表示します。 このセクションで説明および Visual Studio (設計時) からのバインドのプロパティを設定する方法について、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール (実行時)。 デザイン時に、特定の操作のスキーマを生成するバインドのプロパティを指定する必要があります。 、実行時に、送信の一部としてのバインドのプロパティを指定か、SAP システムからメッセージを送受信するためのポートが表示される必要があります。  
  
 バインドのプロパティについては、バインドのプロパティの一覧を含む[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を参照してください[mySAP Business Suite のバインドのプロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)です。  
  
## <a name="enter-binding-properties-at-design-time"></a>デザイン時のバインドのプロパティを入力してください。  
 デザイン時を使用してバインドのプロパティを指定できます、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]です。  
  
### <a name="enter-binding-properties-using-consume-adapter-service-add-in"></a>アダプター サービスのアドインを使用してバインドのプロパティを入力してください。  
  
1.  BizTalk プロジェクトを右クリックし、順にポイント**追加**、クリックして**生成した項目の追加**です。  
  
2.  **生成した項目の追加** ダイアログ ボックスで、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**カテゴリ**|をクリックして**アダプター サービスの使用**です。|  
    |**[テンプレート]**|をクリックして**アダプター サービスの使用**です。|  
  
3.  開始する、**アダプター サービスの使用**ダイアログ ボックスで、をクリックして**追加**です。  
  
4.  **アダプター サービスの使用** ダイアログ ボックスから、**バインディングを選択**ドロップダウン リストを**sapBinding**、 をクリック**構成**.  
  
5.  **アダプターの構成**ダイアログ ボックスで、をクリックして、**バインド プロパティ**タブをクリックし、別のバインディング プロパティを指定します。  
  
6.  **[OK]**をクリックします。  
  
### <a name="enter-binding-properties-using-add-adapter-metadata-wizard"></a>アダプター メタデータの追加ウィザードを使用してバインドのプロパティを入力してください。  
  
1.  BizTalk プロジェクトを右クリックし、順にポイント**追加**、クリックして**生成した項目の追加**です。  
  
2.  **生成した項目の追加** ダイアログ ボックスで、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**カテゴリ**|をクリックして**アダプターを追加**です。|  
    |**[テンプレート]**|をクリックして**アダプター メタデータの追加**です。|  
  
3.  **[追加]**をクリックします。 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] が表示されます。  
  
4.  アダプターの追加ウィザードで選択**WCF SAP**です。 BizTalk Server がインストールされているコンピューターを選択し、BizTalk データベースの名前。  
  
    > [!IMPORTANT]
    >  BizTalk で構成されている WCF SAP ポートがある場合からポートを選択して、**ポート** ボックスの一覧です。  
  
5.  **[次へ]**をクリックします。  
  
6.  **アダプター サービスの使用** ダイアログ ボックスから、**バインディングを選択**ドロップダウン リストを**sapBinding**、 をクリック**構成**.  
  
7.  クリックして、**バインド プロパティ** タブの値を指定します、バインディング、存在する場合は、スキーマを生成する前に指定する必要です。 たとえばの値を指定する必要があります、 **GenerateFlatFileCompatibleIDoc** SAP システムから IDOC を受信するためのスキーマを生成する前にプロパティです。 バインドのプロパティの詳細については、次を参照してください。 [mySAP Business Suite のバインドのプロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)です。  
  
    > [!NOTE]
    >  既存の SAP WCF 送信ポートを選択した場合、バインドのプロパティを指定する必要はありません。 バインドのプロパティは、送信ポートの構成から取得されます。 ただし、存在する場合、デザイン時に、必要なバインドのプロパティを指定することもできます。 このような場合、メタデータの生成中にバインドのプロパティの新しい値をデザイン時に使用されます。 ただし、実行時に、バインドの送信ポートの構成のプロパティの指定値適用されます。  
  
8.  **[OK]**をクリックします。  
  
## <a name="enter-binding-properties-at-run-time"></a>実行時のバインドのプロパティを入力してください。  
 実行時は、WCF カスタム ポートまたはで WCF SAP 構成の一部としてのバインドのプロパティを指定できます、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
### <a name="enter-binding-properties-for-the-wcf-custom-port"></a>WCF カスタム ポートのバインドのプロパティを入力します。  
  
1.  開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
2.  コンソール ツリーで  **BizTalk グループ**の順に展開**アプリケーション**、ポートを作成し、をクリックする、アプリケーションの順に展開および**送信ポート**または**受信ポート**です。 右側のウィンドウでは、ポートを作成または既存のポートを選択できます。  
  
3.  **ポートのプロパティ** ダイアログ ボックスから、**型**ドロップダウン リストで、 **Wcf-custom**をクリックし、**構成**です。  
  
    > [!NOTE]
    >  受信ポートの場所のプロパティ ダイアログ ボックスを表示するをクリックして、**受信場所の**ポートのプロパティ ダイアログ ボックスの左側のウィンドウでタブをクリックして**新規**です。  
  
4.  **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**バインド**タブです。  
  
5.  **バインディングの種類**ドロップダウン リストで、 **sapBinding**です。  
  
6.  **構成**ボックスで異なるバインディングのプロパティの値を指定し、をクリックして**OK**です。  
  
### <a name="enter-binging-properties-for-the-wcf-sap-port"></a>WCF SAP ポートのバインドのプロパティを入力します。  
  
1.  開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
2.  WCF SAP アダプターを追加、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 手順については、次を参照してください。 [SAP アダプターを BizTalk Server 管理コンソールに追加](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md)です。  
  
3.  コンソール ツリーで  **BizTalk グループ**の順に展開**アプリケーション**、ポートを作成し、をクリックする、アプリケーションの順に展開および**送信ポート**または**受信ポート**です。 右側のウィンドウでは、ポートを作成または既存のポートを選択できます。  
  
4.  ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストは、前に追加する WCF SAP アダプターを選択し、をクリックして**構成**です。  
  
    > [!NOTE]
    >  受信ポートの場所のプロパティ ダイアログ ボックスを表示するをクリックして、**受信場所の**ポートのプロパティ ダイアログ ボックスの左側のウィンドウでタブをクリックして**新規**です。  
  
5.  トランスポートのプロパティ ダイアログ ボックスをクリックして、**バインディング**タブし、バインドのプロパティの値を指定します。  
  
    > [!NOTE]
    >  バインドのプロパティは、送信ポートまたは受信ポートを構成するかどうかに基づいてが表示されます。 たとえば、バインディングのプロパティの受信に関連する操作利用できない受信操作には、受信ポートの構成が必要とするために、送信ポートを構成するときにします。  
  
6.  **[OK]**をクリックします。  
  
## <a name="see-also"></a>参照  
[SAP アプリケーションを作成する構成要素](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)