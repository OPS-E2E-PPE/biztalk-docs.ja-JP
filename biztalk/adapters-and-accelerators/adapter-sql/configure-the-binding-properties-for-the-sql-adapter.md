---
title: "SQL アダプターのバインドのプロパティを構成する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c2edbd90-039a-48b4-a6fc-d825b4957207
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 42576a59aae28c78250f5eba19558072e0e526d0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configure-the-binding-properties-for-the-sql-adapter"></a>SQL アダプターのバインドのプロパティを構成します。
[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]動作特性を制御できるようにするいくつかのバインドのプロパティを表示します。 このセクションで説明からのバインドのプロパティを設定する方法について[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]との間、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、特定の操作のスキーマを生成するバインドのプロパティを指定する必要があります。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]送信の一部としてのバインドのプロパティを指定または SQL Server からメッセージを送受信するためのポートを受信する必要があります。  
  
 バインドのプロパティについては、バインドのプロパティの一覧を含め、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を参照してください[SQL Server のアダプターのバインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)です。  
  
## <a name="enter-the-binding-properties-in-visual-studio"></a>Visual Studio でのバインドのプロパティを入力してください。  
 [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]を使用してバインドのプロパティを指定することができます、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]です。  
  
### <a name="using-consume-adapter-service-add-in"></a>使用してアダプターを使用する追加のサービス  
  
1.  BizTalk プロジェクトを右クリックし **生成した項目の追加**です。  
  
2.  **生成した項目の追加** ダイアログ ボックスで、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**カテゴリ**|をクリックして**アダプター サービスの使用**です。|  
    |**[テンプレート]**|をクリックして**アダプター サービスの使用**です。|  
  
3.  開始する、**アダプター サービスの使用**ダイアログ ボックスで、をクリックして**追加**です。  
  
4.  **アダプター サービスの使用** ダイアログ ボックスから、**バインディングを選択**ドロップダウン リスト、選択**sqlBinding**、順にクリック**構成**.  
  
5.  **アダプターの構成**ダイアログ ボックスで、をクリックして、**バインド プロパティ**タブをクリックし、別のバインディング プロパティを指定します。  
  
6.  **[OK]**をクリックします。  
  
### <a name="using-add-adapter-metadata-wizard"></a>アダプター メタデータのウィザードを使用して追加  
  
1.  BizTalk プロジェクトを右クリックし、**追加**、クリックして**生成した項目の追加**です。  
  
2.  **生成した項目の追加** ダイアログ ボックスで、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**カテゴリ**|をクリックして**アダプターを追加**です。|  
    |**[テンプレート]**|をクリックして**アダプター メタデータの追加**です。|  
  
3.  **[追加]**をクリックします。 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] が表示されます。  
  
4.  アダプターの追加ウィザードで選択**WCF-SQL**です。 BizTalk Server がインストールされているコンピューターを選択し、BizTalk データベースの名前。  
  
    > [!IMPORTANT]
    >  BizTalk で構成されている WCF SQL ポートがある場合からポートを選択して、**ポート** ボックスの一覧です。  
  
5.  **[次へ]**をクリックします。  
  
6.  **アダプター サービスの使用** ダイアログ ボックスから、**バインディングを選択**ドロップダウン リスト、選択**sqlBinding**、順にクリック**構成**.  
  
7.  クリックして、**バインド プロパティ**タブをクリックし、対象となる操作で、必要な場合、バインド プロパティの値を指定します。 バインドのプロパティの詳細については、次を参照してください。 [SQL Server のアダプターのバインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)です。  
  
    > [!NOTE]
    >  既存の WCF-SQL 送信ポートを選択した場合、バインドのプロパティを指定する必要はありません。 バインドのプロパティは、送信ポートの構成から取得されます。 ただし、存在する場合、デザイン時に、必要なバインドのプロパティを指定することもできます。 このような場合、メタデータの生成中にバインドのプロパティの新しい値をデザイン時に使用されます。 ただし、実行時に、バインドの送信ポートの構成のプロパティの指定値適用されます。  
  
8.  **[OK]**をクリックします。  
  
## <a name="enter-binding-properties-from-the-biztalk-server-administration-console"></a>BizTalk Server 管理コンソールからバインドのプロパティを入力してください。  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、Wcf-custom または WCF SQL ポートの構成の一部としてのバインドのプロパティを指定できます。  
  
### <a name="enter-binding-properties-for-wcf-custom-port"></a>WCF カスタム ポートのバインドのプロパティを入力してください。  
  
1.  開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
2.  コンソール ツリーで  **BizTalk グループ**の順に展開**アプリケーション**、ポートを作成し、をクリックする、アプリケーションの順に展開および**送信ポート**または**受信ポート**です。 右側のウィンドウでは、ポートを作成または既存のポートを選択できます。  
  
3.  ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストで、 **Wcf-custom**、クリックして**構成**です。  
  
    > [!NOTE]
    >  受信ポートの場所のプロパティ ダイアログ ボックスを表示するをクリックして、**受信場所の**ポートのプロパティ ダイアログ ボックスの左側のウィンドウでタブをクリックして**新規**です。  
  
4.  **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**バインド**タブです。  
  
5.  **バインディングの種類**一覧で、 **sqlBinding**です。  
  
6.  **構成**ボックスで異なるバインディングのプロパティの値を指定し、をクリックして**OK**です。  
  
### <a name="enter-binding-properties-for-the-wcf-sql-port"></a>WCF SQL ポートのバインドのプロパティを入力します。  
  
1.  開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
2.  WCF-SQL アダプターの追加、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 手順については、次を参照してください。 [SQL アダプタを BizTalk Server 管理コンソールに追加する](../../adapters-and-accelerators/adapter-sql/adding-the-sql-adapter-to-biztalk-server-administration-console.md)です。  
  
3.  コンソール ツリーで  **BizTalk グループ**の順に展開**アプリケーション**、ポートを作成し、をクリックする、アプリケーションの順に展開および**送信ポート**または**受信ポート**です。 右側のウィンドウでは、ポートを作成または既存のポートを選択できます。  
  
4.  ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストは、前に追加する WCF-SQL アダプターを選択し、をクリックして**構成**です。  
  
    > [!NOTE]
    >  受信ポートの場所のプロパティ ダイアログ ボックスを表示するをクリックして、**受信場所の**ポートのプロパティ ダイアログ ボックスの左側のウィンドウでタブをクリックして**新規**です。  
  
5.  トランスポートのプロパティ ダイアログ ボックスをクリックして、**バインディング**タブし、バインドのプロパティの値を指定します。  
  
    > [!NOTE]
    >  バインドのプロパティは、送信ポートまたは受信ポートを構成するかどうかに基づいてが表示されます。 たとえば、通知に関連するバインド プロパティ利用できない通知が受信操作には、受信ポートの構成を必要とするために、送信ポートを構成するときにします。  
  
6.  **[OK]**をクリックします。  
  
## <a name="see-also"></a>参照  
[SQL アダプタを BizTalk アプリケーションを開発する構成要素](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)