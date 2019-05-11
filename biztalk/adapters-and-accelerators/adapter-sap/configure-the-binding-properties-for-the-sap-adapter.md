---
title: SAP アダプターのバインドのプロパティの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- binding properties, specifying at design time
- binding properties, specifying at run time
ms.assetid: 259a5895-c19d-409c-b2fc-bfdf59d5d74b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ecdb5cf06e16c6844addea9e4b7f8fb5f8903bba
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373869"
---
# <a name="configure-the-binding-properties-for-the-sap-adapter"></a>SAP アダプターのバインドのプロパティを構成します。
[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]動作特性を制御するためのいくつかのバインドのプロパティを表示します。 このセクションでは、および Visual Studio (デザイン時) からバインドのプロパティを設定する方法についての情報を提供します。、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールを (実行時)。 デザイン時に、特定の操作のスキーマを生成するバインドのプロパティを指定する必要があります。 実行時にには、送信の一部としてのバインドのプロパティを指定または SAP システムからのメッセージの送受信用のポートを受信する必要があります。  

 バインドのプロパティについては、バインドのプロパティの一覧を含む[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を参照してください[mySAP Business Suite のバインドのプロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)します。  

## <a name="enter-binding-properties-at-design-time"></a>デザイン時のバインドのプロパティを入力します。  
 デザイン時に、バインドのプロパティを使用して指定できます、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]します。  

### <a name="enter-binding-properties-using-consume-adapter-service-add-in"></a>Consume Adapter Service アドインを使用してバインドのプロパティを入力します。  

1.  BizTalk プロジェクトを右クリックし、[**追加**、] をクリックし、**生成した項目の追加**します。  

2.  **生成した項目の追加** ダイアログ ボックスで、次の操作を行います。  

    |プロパティ|目的|  
    |--------------|----------------|  
    |**カテゴリ**|クリックして**アダプター サービスの使用**します。|  
    |**[テンプレート]**|クリックして**アダプター サービスの使用**します。|  

3.  開始する、 **Consume Adapter Service**ダイアログ ボックスで、をクリックして**追加**します。  

4.  **Consume Adapter Service**  ダイアログ ボックスから、**バインディングを選択**ドロップダウン リストを**sapBinding**、 をクリック**構成**.  

5.  **アダプターの構成**ダイアログ ボックスで、をクリックして、**バインド プロパティ**タブをクリックし、別のバインド プロパティを指定します。  

6.  **[OK]** をクリックします。  

### <a name="enter-binding-properties-using-add-adapter-metadata-wizard"></a>アダプター メタデータの追加ウィザードを使用してバインドのプロパティを入力します。  

1. BizTalk プロジェクトを右クリックし、[**追加**、] をクリックし、**生成した項目の追加**します。  

2. **生成した項目の追加** ダイアログ ボックスで、次の操作を行います。  


   |    プロパティ    |           目的            |
   |----------------|---------------------------------|
   | **カテゴリ** |     クリックして**アダプターを追加**します。      |
   | **[テンプレート]**  | クリックして**アダプター メタデータの追加**します。 |


3. **[追加]** をクリックします。 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] が表示されます。  

4. アダプターの追加ウィザードで選択**WCF-SAP**します。 BizTalk Server がインストールされているコンピューターを選択し、BizTalk データベースの名前。  

   > [!IMPORTANT]
   >  BizTalk で構成されている WCF SAP ポート既にある場合からポートを選択して、**ポート**一覧。  

5. **[次へ]** をクリックします。  

6. **Consume Adapter Service**  ダイアログ ボックスから、**バインディングを選択**ドロップダウン リストを**sapBinding**、 をクリック**構成**.  

7. をクリックして、**バインドのプロパティ**タブし、バインドの値を指定、存在する場合は、スキーマを生成する前に指定するために必要です。 たとえばの値を指定する必要があります、 **GenerateFlatFileCompatibleIDoc** SAP システムから IDOC を受信するためのスキーマを生成する前にプロパティ。 バインド プロパティの詳細については、次を参照してください。 [mySAP Business Suite のバインドのプロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)します。  

   > [!NOTE]
   >  既存の SAP では WCF 送信ポートを選択した場合は、バインドのプロパティを指定する必要がありますできません。 バインドのプロパティは、送信ポートの構成から取得されます。 ただし、存在する場合に、デザイン時に必要なバインドのプロパティを指定することができます。 このような場合、メタデータの生成中にプロパティをバインドするための新しい値をデザイン時に使用されます。 ただし、実行時に送信ポートの構成でバインドのプロパティに指定された値を適用できるになります。  

8. **[OK]** をクリックします。  

## <a name="enter-binding-properties-at-run-time"></a>実行時のバインドのプロパティを入力します。  
 WCF カスタム ポートまたは WCF SAP 構成の一部としてのバインドのプロパティを指定する、実行時に、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  

### <a name="enter-binding-properties-for-the-wcf-custom-port"></a>WCF カスタム ポートのバインドのプロパティを入力します。  

1. 開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  

2. コンソール ツリーで、展開**BizTalk グループ**の順に展開**アプリケーション**、順に展開する、ポートを作成し、をクリックしアプリケーション**送信ポート**または**受信ポート**します。 右側のウィンドウでは、ポートを作成または既存のポートを選択できます。  

3. **ポートのプロパティ** ダイアログ ボックスから、**型**ドロップダウン リストで、 **Wcf-custom**、順にクリックします**構成**します。  

   > [!NOTE]
   >  受信ポートの場所のプロパティ ダイアログ ボックスを表示する をクリックして、**受信場所**ポートのプロパティ ダイアログ ボックスの左側のウィンドウでタブをクリックして**新規**します。  

4. **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**バインド**タブ。  

5. **バインドの種類**ドロップダウン リストで、 **sapBinding**します。  

6. **構成**ボックスに、さまざまなバインドのプロパティの値を指定してクリックして**OK**。  

### <a name="enter-binging-properties-for-the-wcf-sap-port"></a>WCF SAP ポートのバインドのプロパティを入力します。  

1. 開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  

2. WCF-SAP アダプターの追加、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 手順については、次を参照してください。 [SAP アダプターを BizTalk Server 管理コンソールに追加](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md)します。  

3. コンソール ツリーで、展開**BizTalk グループ**の順に展開**アプリケーション**、順に展開する、ポートを作成し、をクリックしアプリケーション**送信ポート**または**受信ポート**します。 右側のウィンドウでは、ポートを作成または既存のポートを選択できます。  

4. ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストでは、先ほど追加した WCF-SAP アダプターを選択し、順にクリックします**構成**します。  

   > [!NOTE]
   >  受信ポートの場所のプロパティ ダイアログ ボックスを表示する をクリックして、**受信場所**ポートのプロパティ ダイアログ ボックスの左側のウィンドウでタブをクリックして**新規**します。  

5. トランスポートのプロパティ ダイアログ ボックスでをクリックして、**バインド**タブし、バインドのプロパティの値を指定します。  

   > [!NOTE]
   >  バインドのプロパティは、送信ポートまたは受信ポートを構成するかどうかに基づいて表示されます。 たとえば、バインディングのプロパティに関連する受信操作をご利用いただけません受信操作には、受信ポートの構成が必要とするために、送信ポートを構成するときに。  

6. **[OK]** をクリックします。  

## <a name="see-also"></a>参照  
[SAP アプリケーションを作成するための構成要素](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)