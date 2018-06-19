---
title: Oracle データベースのバインド プロパティの構成 |Microsoft ドキュメント
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
ms.openlocfilehash: 73b7a5205b2fbfe0bc42bf5af0930356a003d5be
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22215802"
---
# <a name="configure-the-binding-properties-for-oracle-database"></a>Oracle データベースのバインドのプロパティを構成します。
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]動作特性を制御できるようにするいくつかのバインドのプロパティを表示します。 このセクションでは、Visual Studio および BizTalk Server 管理コンソールからバインドのプロパティの設定に関する情報を提供します。 Visual Studio から、特定の操作のスキーマの生成中にバインドのプロパティを指定する必要があります。 BizTalk Server からには、送信の一部としてのバインドのプロパティを指定または Oracle データベースからメッセージを送受信するためのポートを受信する必要があります。  
  
 バインドのプロパティについては、バインドのプロパティの一覧を含む[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を参照してください[Oracle データベース アダプターのバインドのプロパティについてお読み](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)です。  
  
## <a name="specifying-binding-properties-from-visual-studio"></a>Visual Studio からバインドのプロパティを指定します。  
 Visual studio を使用して資格情報を指定する必要があります、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]です。  
  
#### <a name="to-specify-binding-properties-using-consume-adapter-service-add-in"></a>アダプター サービスのアドインを使用してバインド プロパティを指定するには  
  
1.  BizTalk プロジェクトを右クリックし **生成した項目の追加**です。  
  
2.  **生成した項目の追加** ダイアログ ボックスで、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**カテゴリ**|をクリックして**アダプター サービスの使用**です。|  
    |**[テンプレート]**|をクリックして**アダプター サービスの使用**です。|  
  
3.  開始する、**アダプター サービスの使用**ダイアログ ボックスで、をクリックして**追加**です。  
  
4.  **アダプター サービスの使用** ダイアログ ボックスから、**バインディングを選択**ドロップダウン リストを**oracleDBBinding**、 をクリック**構成**.  
  
5.  **アダプターの構成**ダイアログ ボックスで、をクリックして、**バインド プロパティ**タブし、さまざまなバインドのプロパティを指定します。  
  
6.  **[OK]** をクリックします。  
  
#### <a name="to-specify-binding-properties-using-add-adapter-metadata-wizard"></a>アダプター メタデータの追加ウィザードを使用してバインド プロパティを指定するには  
  
1.  BizTalk プロジェクトを右クリックし **生成した項目の追加**です。  
  
2.  **生成した項目の追加** ダイアログ ボックスで、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**カテゴリ**|をクリックして**アダプターを追加**です。|  
    |**[テンプレート]**|をクリックして**アダプター メタデータの追加**です。|  
  
3.  **[追加]** をクリックします。 アダプター メタデータの追加ウィザードが開きます。  
  
4.  アダプター メタデータの追加ウィザードで選択**Wcf-oracledb**です。 コンピューターを選択して[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]がインストールされていると、BizTalk データベースの名前。  
  
    > [!IMPORTANT]
    >  BizTalk で構成された Wcf-oracledb ポートがある場合からポートを選択して、**ポート** ボックスの一覧です。  
  
5.  **[次へ]** をクリックします。  
  
6.  **アダプター サービスの使用** ダイアログ ボックスから、**バインディングを選択**ドロップダウン リストを**oracleDBBinding**、 をクリック**構成**.  
  
7.  **アダプターの構成**ダイアログ ボックスで、をクリックして、**バインドのプロパティ**タブをクリックし、バインディングの値を指定、存在する場合、スキーマを生成する前に必要とします。 バインドのプロパティの詳細については、次を参照してください。 [Oracle データベース アダプターのバインドのプロパティについてお読み](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)です。  
  
    > [!NOTE]
    >  既存の Wcf-oracledb 送信ポートを選択した場合、バインドのプロパティを指定する必要はありません。 バインドのプロパティは、送信ポートの構成から取得されます。 ただし、存在する場合、デザイン時に、必要なバインドのプロパティを指定することもできます。 このような場合は、バインドのプロパティの新しい値は、メタデータの生成中のデザイン時に使用されます。 ただし、実行時に、バインドの送信ポートの構成のプロパティの指定値適用されます。  
  
8.  **[OK]** をクリックします。  
  
## <a name="specifying-binding-properties-from-the-biztalk-server-administration-console"></a>BizTalk Server 管理コンソールからバインドのプロパティを指定します。  
 BizTalk Server 管理コンソールから Wcf-custom または Wcf-oracledb ポートの構成の一部としてのバインドのプロパティを指定する必要があります。  
  
#### <a name="to-specify-binding-properties-for-the-wcf-custom-port"></a>WCF カスタム ポートのバインド プロパティを指定するには  
  
1.  開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
2.  コンソール ツリーで  **BizTalk グループ**の順に展開**アプリケーション**、ポートを作成し、をクリックする、アプリケーションの順に展開および**送信ポート**または**受信ポート**です。 右側のウィンドウでは、ポートを作成または既存のポートを選択できます。  
  
3.  ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストで、 **Wcf-custom**、クリックして**構成**です。  
  
    > [!NOTE]
    >  受信ポートの場所のプロパティ ダイアログ ボックスを表示するをクリックして、**受信場所の**ポートのプロパティ ダイアログ ボックスの左側のウィンドウでタブをクリックして**新規**です。  
  
4.  **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**バインド**タブです。  
  
5.  **バインディングの種類**ドロップダウン リストで、 **oracleDBBinding**です。  
  
6.  **構成**ボックスで異なるバインディングのプロパティの値を指定し、をクリックして**OK**です。  
  
#### <a name="to-specify-binding-properties-for-the-wcf-oracledb-port"></a>Wcf-oracledb ポートのバインド プロパティを指定するには  
  
1.  開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
2.  Wcf-oracledb アダプターを BizTalk Server 管理コンソールに追加します。 手順については、次を参照してください。 [BizTalk Server 管理コンソールへの Oracle データベース アダプターの追加](../../adapters-and-accelerators/adapter-oracle-database/adding-the-oracle-database-adapter-to-biztalk-server-administration-console.md)です。  
  
3.  コンソール ツリーで  **BizTalk グループ**の順に展開**アプリケーション**、ポートを作成し、をクリックする、アプリケーションの順に展開および**送信ポート**または**受信ポート**です。 右側のウィンドウでは、ポートを作成または既存のポートを選択できます。  
  
4.  ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストは、前に追加する Wcf-oracledb アダプターを選択し、をクリックして**構成**です。  
  
    > [!NOTE]
    >  受信ポートの場所のプロパティ ダイアログ ボックスを表示するをクリックして、**受信場所の**ポートのプロパティ ダイアログ ボックスの左側のウィンドウでタブをクリックして**新規**です。  
  
5.  トランスポートのプロパティ ダイアログ ボックスをクリックして、**バインディング**タブをクリックし、バインドのプロパティの値を指定します。  
  
    > [!NOTE]
    >  バインドのプロパティは、送信ポートまたは受信ポートを構成するかどうかに基づいてが表示されます。 たとえば、通知に関連するバインド プロパティ利用できない通知が受信操作には、受信ポートの構成を必要とするために、送信ポートを構成するときにします。  
  
## <a name="see-also"></a>参照  
[Oracle データベースと BizTalk アプリケーションを開発する構成要素](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)