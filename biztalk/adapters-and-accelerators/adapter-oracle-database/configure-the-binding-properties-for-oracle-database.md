---
title: Oracle データベースのバインド プロパティの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- binding properties, specifying at run time
- binding properties, specifying at design time
ms.assetid: c59a1b5c-b52b-4161-82de-c4d89bfce5c7
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 96922feab7c343893bfaa04ccbccd7c7e2f6a743
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981083"
---
# <a name="configure-the-binding-properties-for-oracle-database"></a>Oracle データベースのバインド プロパティを構成します。
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]動作特性を制御するためのいくつかのバインドのプロパティを表示します。 このセクションでは、Visual Studio と BizTalk Server 管理コンソールから、バインドのプロパティを設定する方法についての情報を提供します。 Visual studio で、特定の操作のスキーマの生成中にバインディング プロパティを指定する必要があります。 BizTalk Server からには、送信の一部としてのバインドのプロパティを指定または Oracle データベースからのメッセージの送受信用のポートを受信する必要があります。  

 バインドのプロパティについては、バインドのプロパティの一覧を含む[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を参照してください[Oracle データベース アダプターのバインドのプロパティについて](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)します。  

## <a name="specifying-binding-properties-from-visual-studio"></a>Visual Studio からバインドのプロパティを指定します。  
 Visual studio を使用して資格情報を指定する必要があります、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]します。  

#### <a name="to-specify-binding-properties-using-consume-adapter-service-add-in"></a>Consume Adapter Service アドインを使用してバインドのプロパティを指定するには  

1.  BizTalk プロジェクトを右クリックし、**生成した項目の追加**します。  

2.  **生成した項目の追加** ダイアログ ボックスで、次の操作を行います。  

    |プロパティ|目的|  
    |--------------|----------------|  
    |**カテゴリ**|クリックして**アダプター サービスの使用**します。|  
    |**[テンプレート]**|クリックして**アダプター サービスの使用**します。|  

3.  開始する、 **Consume Adapter Service**ダイアログ ボックスで、をクリックして**追加**します。  

4.  **Consume Adapter Service**  ダイアログ ボックスから、**バインディングを選択**ドロップダウン リストを**oracleDBBinding**、 をクリック**構成**.  

5.  **アダプターの構成**ダイアログ ボックスで、をクリックして、**バインドのプロパティ**タブし、さまざまなバインドのプロパティを指定します。  

6.  **[OK]** をクリックします。  

#### <a name="to-specify-binding-properties-using-add-adapter-metadata-wizard"></a>アダプター メタデータの追加ウィザードを使用してバインドのプロパティを指定するには  

1. BizTalk プロジェクトを右クリックし、**生成した項目の追加**します。  

2. **生成した項目の追加** ダイアログ ボックスで、次の操作を行います。  


   |    プロパティ    |           目的            |
   |----------------|---------------------------------|
   | **カテゴリ** |     クリックして**アダプターを追加**します。      |
   | **[テンプレート]**  | クリックして**アダプター メタデータの追加**します。 |


3. **[追加]** をクリックします。 アダプター メタデータの追加ウィザードが開きます。  

4. アダプター メタデータの追加ウィザードで選択**Wcf-oracledb**します。 コンピューターを選択します。[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]がインストールされていると、BizTalk データベースの名前。  

   > [!IMPORTANT]
   >  BizTalk で構成された Wcf-oracledb ポート既にある場合からポートを選択して、**ポート**一覧。  

5. **[次へ]** をクリックします。  

6. **Consume Adapter Service**  ダイアログ ボックスから、**バインディングを選択**ドロップダウン リストを**oracleDBBinding**、 をクリック**構成**.  

7. **アダプターの構成**ダイアログ ボックスで、をクリックして、**バインド プロパティ**タブをクリックし、バインドの値を指定、存在する場合、スキーマを生成する前に必要な。 バインド プロパティの詳細については、次を参照してください。 [Oracle データベース アダプターのバインドのプロパティについて](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)します。  

   > [!NOTE]
   >  既存の Wcf-oracledb 送信ポートを選択した場合は、バインドのプロパティを指定する必要がありますできません。 バインドのプロパティは、送信ポートの構成から取得されます。 ただし、存在する場合に、デザイン時に必要なバインドのプロパティを指定することができます。 このような場合は、メタデータの生成中にプロパティをバインドするための新しい値をデザイン時に使用されます。 ただし、実行時に送信ポートの構成でバインドのプロパティに指定された値を適用できるになります。  

8. **[OK]** をクリックします。  

## <a name="specifying-binding-properties-from-the-biztalk-server-administration-console"></a>BizTalk Server 管理コンソールからバインドのプロパティを指定します。  
 BizTalk Server 管理コンソールで、Wcf-custom または Wcf-oracledb ポート構成の一部としてのバインドのプロパティを指定する必要があります。  

#### <a name="to-specify-binding-properties-for-the-wcf-custom-port"></a>WCF カスタム ポートのバインドのプロパティを指定するには  

1. 開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  

2. コンソール ツリーで、展開**BizTalk グループ**の順に展開**アプリケーション**、順に展開する、ポートを作成し、をクリックしアプリケーション**送信ポート**または**受信ポート**します。 右側のウィンドウでは、ポートを作成または既存のポートを選択できます。  

3. ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストで、 **Wcf-custom**、 をクリックし、**構成**します。  

   > [!NOTE]
   >  受信ポートの場所のプロパティ ダイアログ ボックスを表示する をクリックして、**受信場所**ポートのプロパティ ダイアログ ボックスの左側のウィンドウでタブをクリックして**新規**します。  

4. **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**バインド**タブ。  

5. **バインドの種類**ドロップダウン リストで、 **oracleDBBinding**します。  

6. **構成**ボックスでのさまざまなバインドのプロパティの値を指定し、をクリックして**OK**します。  

#### <a name="to-specify-binding-properties-for-the-wcf-oracledb-port"></a>Wcf-oracledb ポートのバインドのプロパティを指定するには  

1. 開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  

2. Wcf-oracledb アダプターを BizTalk Server 管理コンソールに追加します。 手順については、次を参照してください。[を BizTalk Server 管理コンソールの Oracle データベース アダプターの追加](../../adapters-and-accelerators/adapter-oracle-database/adding-the-oracle-database-adapter-to-biztalk-server-administration-console.md)します。  

3. コンソール ツリーで、展開**BizTalk グループ**の順に展開**アプリケーション**、順に展開する、ポートを作成し、をクリックしアプリケーション**送信ポート**または**受信ポート**します。 右側のウィンドウでは、ポートを作成または既存のポートを選択できます。  

4. ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストでは、先ほど追加した Wcf-oracledb アダプターを選択してをクリックして**構成**します。  

   > [!NOTE]
   >  受信ポートの場所のプロパティ ダイアログ ボックスを表示する をクリックして、**受信場所**ポートのプロパティ ダイアログ ボックスの左側のウィンドウでタブをクリックして**新規**します。  

5. トランスポートのプロパティ ダイアログ ボックスでをクリックして、**バインド**タブをクリックし、バインドのプロパティの値を指定します。  

   > [!NOTE]
   >  バインドのプロパティは、送信ポートまたは受信ポートを構成するかどうかに基づいて表示されます。 たとえば、通知に関連するバインドのプロパティは通知が受信操作には、受信ポートの構成を必要とするために、送信ポートを構成するときに使用できませんなりました。  

## <a name="see-also"></a>参照  
[Oracle データベースと BizTalk アプリケーションを開発する構成要素](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)