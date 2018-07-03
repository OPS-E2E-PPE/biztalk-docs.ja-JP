---
title: Siebel のバインド プロパティの構成 |Microsoft Docs
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
- how to, specify binding properties at design time
- how to, specify binding properties at run time
ms.assetid: 063e9507-8172-4fb0-8b9f-2f95e8a82f21
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e09f3ce0f5e21c6ac1df6bb7c361674629fa4d36
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992367"
---
# <a name="configure-the-binding-properties-for-siebel"></a>Siebel のバインド プロパティを構成します。
[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]動作特性を制御するためのいくつかのバインドのプロパティを表示します。 このセクションでは、および Visual Studio (デザイン時) からバインドのプロパティを設定する方法についての情報を提供します。、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールを (実行時)。 デザイン時に、特定の操作のスキーマを生成するバインドのプロパティを指定する必要があります。 実行時に、Siebel システムへのメッセージを送信するための送信ポートの一部としてのバインドのプロパティを指定する必要があります。  

 バインドのプロパティについては、バインドのプロパティの一覧を含む[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]を参照してください[for Siebel のバインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md)します。  

## <a name="enter-the-binding-properties-at-design-time"></a>デザイン時のバインドのプロパティを入力します。  
 デザイン時からのバインドのプロパティを指定する必要があります、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] ダイアログ ボックス。  

#### <a name="enter-binding-properties-using-consume-adapter-service-add-in"></a>Consume Adapter Service アドインを使用してバインドのプロパティを入力します。  

1.  BizTalk プロジェクトを右クリックし、**追加**、し、**生成した項目の追加**します。  

2.  **生成した項目の追加** ダイアログ ボックスで、次の操作を行います。  

    |プロパティ|目的|  
    |--------------|----------------|  
    |**カテゴリ**|クリックして**アダプター サービスの使用**します。|  
    |**[テンプレート]**|クリックして**アダプター サービスの使用**します。|  

3.  開始する、 **Consume Adapter Service**ダイアログ ボックスで、をクリックして**追加**します。  

4.  **Consume Adapter Service**  ダイアログ ボックスから、**バインディングを選択**ドロップダウン リストを**siebelBinding**、 をクリック**構成**.  

5.  **アダプターの構成**ダイアログ ボックスで、 をクリックして、**バインドのプロパティ**タブし、バインドの値を指定、存在する場合は、スキーマを生成する前に指定するために必要です。 バインド プロパティの詳細については、次を参照してください。 [for Siebel のバインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md)します。  

6.  **[OK]** をクリックします。  

#### <a name="enter-binding-properties-using-add-adapter-metadata-wizard"></a>アダプター メタデータの追加ウィザードを使用してバインドのプロパティを入力します。  

1. BizTalk プロジェクトを右クリックし、**追加**、し、**生成した項目の追加**します。  

2. **生成した項目の追加** ダイアログ ボックスで、次の操作を行います。  


   |    プロパティ    |           目的            |
   |----------------|---------------------------------|
   | **カテゴリ** |     クリックして**アダプターを追加**します。      |
   | **[テンプレート]**  | クリックして**アダプター メタデータの追加**します。 |


3. **[追加]** をクリックします。 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] が表示されます。  

4. アダプターの追加ウィザードで選択**Wcf-siebel**します。 コンピューターを選択します。[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]がインストールされていると、BizTalk データベースの名前。  

   > [!IMPORTANT]
   >  BizTalk で構成された Wcf-siebel ポート既にある場合からポートを選択して、**ポート**一覧。  

5. **[次へ]** をクリックします。  

6. **Consume Adapter Service**  ダイアログ ボックスから、**バインディングを選択**ドロップダウン リストを**siebelBinding**、 をクリック**構成**.  

7. **アダプターの構成**ダイアログ ボックスで、 をクリックして、**バインドのプロパティ**タブし、バインドの値を指定、存在する場合は、スキーマを生成する前に指定するために必要です。 バインド プロパティの詳細については、次を参照してください。 [for Siebel のバインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md)します。  

   > [!NOTE]
   >  既存の WCF Siebel 送信ポートを選択した場合は、バインドのプロパティを指定する必要がありますできません。 バインドのプロパティは、送信ポートの構成から取得されます。 ただし、存在する場合に、デザイン時に必要なバインドのプロパティを指定することができます。 このような場合、メタデータの生成中にプロパティをバインドするための新しい値をデザイン時に使用されます。 ただし、実行時に送信ポートの構成でバインドのプロパティに指定された値を適用できるになります。  

8. **[OK]** をクリックします。  

## <a name="enter-binding-properties-at-run-time"></a>実行時のバインドのプロパティを入力します。  
 実行時に、Wcf-custom またはで Wcf-siebel ポートの構成の一部としてのバインドのプロパティを指定する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  

#### <a name="enter-binding-properties-for-the-wcf-custom-port"></a>WCF カスタム ポートのバインドのプロパティを入力します。  

1. 開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  

2. コンソール ツリーで、展開**BizTalk グループ**の順に展開**アプリケーション**をクリックして、ポートを作成するアプリケーションを展開し**送信ポート**. 右側のウィンドウでは、ポートを作成または既存のポートを選択できます。  

3. **ポートのプロパティ** ダイアログ ボックスから、**型**ドロップダウン リストで、 **Wcf-custom**、順にクリックします**構成**します。  

4. **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**バインド**タブ。  

5. **バインドの種類**ドロップダウン リストで、 **siebelBinding**します。  

6. **構成**ボックスでのさまざまなバインドのプロパティの値を指定し、をクリックして**OK**します。  

#### <a name="enter-binding-properties-for-the-wcf-siebel-port"></a>Wcf-siebel ポートのバインドのプロパティを入力します。  

1. 開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  

2. Wcf-siebel アダプターの追加、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 手順については、次を参照してください。 [Siebel アダプターを BizTalk Server 管理コンソールに追加](../../adapters-and-accelerators/adapter-siebel/add-the-siebel-adapter-to-biztalk-server-administration-console.md)します。  

3. コンソール ツリーで、展開**BizTalk グループ**の順に展開**アプリケーション**をクリックして、ポートを作成するアプリケーションを展開し**送信ポート**. 右側のウィンドウでは、ポートを作成または既存のポートを選択できます。  

4. **ポートのプロパティ** ダイアログ ボックスから、**型**ボックスの一覧は、先ほど追加した Wcf-siebel ポートを選択し、順にクリックします**構成**します。  

5. トランスポートのプロパティ ダイアログ ボックスでをクリックして、**バインド**タブし、バインドのプロパティの値を指定します。  

6. **[OK]** をクリックします。  

## <a name="see-also"></a>参照  
[Siebel アダプターを使用した BizTalk アプリケーションを作成する構成要素](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)