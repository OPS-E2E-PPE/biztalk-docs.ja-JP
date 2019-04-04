---
title: SQL アダプタのバインドのプロパティの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c2edbd90-039a-48b4-a6fc-d825b4957207
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 013d9b2b5da755101b53420f2b29fb639851d230
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010067"
---
# <a name="configure-the-binding-properties-for-the-sql-adapter"></a>SQL アダプタのバインドのプロパティを構成します。
[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]動作特性を制御するためのいくつかのバインドのプロパティを表示します。 このセクションでは、バインドのプロパティを設定する方法についての情報を提供します。[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]との間、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、特定の操作のスキーマを生成するバインドのプロパティを指定する必要があります。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]送信の一環としてバインドのプロパティを指定するか、受信ポートを送信または SQL Server からメッセージを受信する必要があります。  

 バインドのプロパティについては、バインドのプロパティの一覧を含む、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を参照してください[for SQL Server のアダプターのバインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)します。  

## <a name="enter-the-binding-properties-in-visual-studio"></a>Visual Studio でのバインドのプロパティを入力します。  
 [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]を使用してバインドのプロパティを指定することができます、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]します。  

### <a name="using-consume-adapter-service-add-in"></a>アダプターを使用してを使用して追加のサービス  

1.  BizTalk プロジェクトを右クリックし、**生成した項目の追加**します。  

2.  **生成した項目の追加** ダイアログ ボックスで、次の操作を行います。  

    |プロパティ|目的|  
    |--------------|----------------|  
    |**カテゴリ**|クリックして**アダプター サービスの使用**します。|  
    |**[テンプレート]**|クリックして**アダプター サービスの使用**します。|  

3.  開始する、 **Consume Adapter Service**ダイアログ ボックスで、をクリックして**追加**します。  

4.  **Consume Adapter Service**  ダイアログ ボックスから、**バインディングを選択**ドロップダウン リスト、選択**sqlBinding**、順にクリックします**構成**.  

5.  **アダプターの構成**ダイアログ ボックスで、をクリックして、**バインド プロパティ**タブをクリックし、別のバインド プロパティを指定します。  

6.  **[OK]** をクリックします。  

### <a name="using-add-adapter-metadata-wizard"></a>アダプター メタデータのウィザードを使用して追加  

1. BizTalk プロジェクトを右クリックし、[**追加**、] をクリックし、**生成した項目の追加**します。  

2. **生成した項目の追加** ダイアログ ボックスで、次の操作を行います。  


   |    プロパティ    |           目的            |
   |----------------|---------------------------------|
   | **カテゴリ** |     クリックして**アダプターを追加**します。      |
   | **[テンプレート]**  | クリックして**アダプター メタデータの追加**します。 |


3. **[追加]** をクリックします。 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] が表示されます。  

4. アダプターの追加ウィザードで選択**WCF-SQL**します。 BizTalk Server がインストールされているコンピューターを選択し、BizTalk データベースの名前。  

   > [!IMPORTANT]
   >  BizTalk で構成されている WCF SQL ポートが既にあるを場合からポートの選択、**ポート**一覧。  

5. **[次へ]** をクリックします。  

6. **Consume Adapter Service**  ダイアログ ボックスから、**バインディングを選択**ドロップダウン リスト、選択**sqlBinding**、順にクリックします**構成**.  

7. をクリックして、**バインド プロパティ**タブをクリックし、対象と操作に必要な場合、バインドのプロパティの値を指定します。 バインド プロパティの詳細については、[for SQL Server のアダプターのバインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)を参照してください。  

   > [!NOTE]
   >  既存の WCF-SQL 送信ポートを選択した場合は、バインドのプロパティを指定する必要がありますできません。 バインドのプロパティは、送信ポートの構成から取得されます。 ただし、存在する場合に、デザイン時に必要なバインドのプロパティを指定することができます。 このような場合、メタデータの生成中にプロパティをバインドするための新しい値をデザイン時に使用されます。 ただし、実行時に送信ポートの構成でバインドのプロパティに指定された値を適用できるになります。  

8. **[OK]** をクリックします。  

## <a name="enter-binding-properties-from-the-biztalk-server-administration-console"></a>BizTalk Server 管理コンソールからバインドのプロパティを入力します。  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、Wcf-custom または WCF SQL ポートの構成の一部としてのバインドのプロパティを指定することができます。  

### <a name="enter-binding-properties-for-wcf-custom-port"></a>WCF カスタム ポートのバインドのプロパティを入力します。  

1. 開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  

2. コンソール ツリーで、展開**BizTalk グループ**の順に展開**アプリケーション**、順に展開する、ポートを作成し、をクリックしアプリケーション**送信ポート**または**受信ポート**します。 右側のウィンドウでは、ポートを作成または既存のポートを選択できます。  

3. ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストで、 **Wcf-custom**、 をクリックし、**構成**します。  

   > [!NOTE]
   >  受信ポートの場所のプロパティ ダイアログ ボックスを表示する をクリックして、**受信場所**ポートのプロパティ ダイアログ ボックスの左側のウィンドウでタブをクリックして**新規**します。  

4. **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**バインド**タブ。  

5. **バインドの種類**一覧で、 **sqlBinding**します。  

6. **構成**ボックスに、さまざまなバインドのプロパティの値を指定してクリックして**OK**。  

### <a name="enter-binding-properties-for-the-wcf-sql-port"></a>WCF SQL ポートのバインドのプロパティを入力します。  

1. 開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  

2. WCF-SQL アダプターを追加、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 手順については、[SQL アダプタを BizTalk Server 管理コンソールに追加する](../../adapters-and-accelerators/adapter-sql/adding-the-sql-adapter-to-biztalk-server-administration-console.md)を参照してください。  

3. コンソール ツリーで、展開**BizTalk グループ**の順に展開**アプリケーション**、順に展開する、ポートを作成し、をクリックしアプリケーション**送信ポート**または**受信ポート**します。 右側のウィンドウでは、ポートを作成または既存のポートを選択できます。  

4. ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストでは、先ほど追加した WCF-SQL アダプターを選択し、順にクリックします**構成**します。  

   > [!NOTE]
   >  受信ポートの場所のプロパティ ダイアログ ボックスを表示する をクリックして、**受信場所**ポートのプロパティ ダイアログ ボックスの左側のウィンドウでタブをクリックして**新規**します。  

5. トランスポートのプロパティ ダイアログ ボックスでをクリックして、**バインド**タブし、バインドのプロパティの値を指定します。  

   > [!NOTE]
   >  バインドのプロパティは、送信ポートまたは受信ポートを構成するかどうかに基づいて表示されます。 たとえば、通知に関連するバインドのプロパティは通知が受信操作には、受信ポートの構成を必要とするために、送信ポートを構成するときに使用できませんなりました。  

6. **[OK]** をクリックします。  

## <a name="see-also"></a>参照  
[SQL アダプターを使用した BizTalk アプリケーションを開発する構成要素](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)