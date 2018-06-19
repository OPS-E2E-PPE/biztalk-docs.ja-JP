---
title: '手順 2: 分類、アダプターとの接続プロパティ |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 45b3dc64-2078-4008-878b-501f727f4a11
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6e9d49323695b1070a8065cf7a5e548e61fc5db9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22226826"
---
# <a name="step-2-categorize-the-adapter-and-connection-properties"></a><span data-ttu-id="dde19-102">手順 2: 分類、アダプターと接続のプロパティ</span><span class="sxs-lookup"><span data-stu-id="dde19-102">Step 2: Categorize the Adapter and Connection Properties</span></span>
<span data-ttu-id="dde19-103">![手順 2 の 9](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-2of9.gif "Step_2of9")</span><span class="sxs-lookup"><span data-stu-id="dde19-103">![Step 2 of 9](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-2of9.gif "Step_2of9")</span></span>  
  
 <span data-ttu-id="dde19-104">**所要時間:** 30 分</span><span class="sxs-lookup"><span data-stu-id="dde19-104">**Time to complete:** 30 minutes</span></span>  
  
 <span data-ttu-id="dde19-105">この手順では更新、 **EchoAdapterBindingElement**と**EchoAdapterBindingElementExtensionElement**アダプターと接続のプロパティをカテゴリに分類するクラス。</span><span class="sxs-lookup"><span data-stu-id="dde19-105">In this step, you update the **EchoAdapterBindingElement** and **EchoAdapterBindingElementExtensionElement** classes to assign a category to your adapter and connection properties.</span></span> <span data-ttu-id="dde19-106">これにより、プロパティは、論理的にグループ化のカテゴリによって、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]と[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]ツールです。</span><span class="sxs-lookup"><span data-stu-id="dde19-106">By doing so, properties are logically grouped by category in the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] and [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] tools.</span></span> <span data-ttu-id="dde19-107">たとえば、する場合は、**アプリケーション**、 **EnableAuthentication**、および**ホスト名**下に表示されるプロパティ、**接続**次のように、カテゴリの各アプリケーション、EnableAuthentication、およびホスト名のプロパティを接続カテゴリを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="dde19-107">For example, if you want the **Application**, **EnableAuthentication**, and **Hostname** properties to appear under the **Connection** category as shown below, you need to assign the Connection category to each of the Application, EnableAuthentication, and Hostname properties.</span></span>  
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/c7c0c013-6651-4c32-9f8b-b546a68a0267.gif "c7c0c013-6651-4c32-9f8b-b546a68a0267")  
  
 <span data-ttu-id="dde19-108">同様に、する場合は、 **InboundFileFilter**と**InboundFleSystemWatcherFolder**下に表示されるプロパティ、**受信**カテゴリで次のように、する必要があります各受信のカテゴリを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="dde19-108">Similarly, if you want the **InboundFileFilter** and **InboundFleSystemWatcherFolder** properties to appear under the **Inbound** category as shown below, you need to assign the Inbound category to each.</span></span> <span data-ttu-id="dde19-109">場合は**カウント**と**EnableConnectionPooling**下に表示される、**その他**カテゴリで、それぞれに、その他のカテゴリを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="dde19-109">If you want **Count** and **EnableConnectionPooling** to appear under the **Misc** category, you need to assign the Misc category to each.</span></span>  
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/2acb7677-8b50-4e45-96a3-42d0e2011f19.gif "2acb7677-8b50-4e45-96a3-42d0e2011f19")  
  
 <span data-ttu-id="dde19-110">選択した任意のカテゴリ名を持つプロパティを割り当てることができることに留意してください。</span><span class="sxs-lookup"><span data-stu-id="dde19-110">Keep in mind that you can assign a property with any category name you choose.</span></span> <span data-ttu-id="dde19-111">この例では EnableConnnectionPooling プロパティは、他のカテゴリに属していませんのでおを分類、その他 (その他)。</span><span class="sxs-lookup"><span data-stu-id="dde19-111">In this example, since the EnableConnnectionPooling property does not belong to any other categories, we categorize it as Misc (Miscellaneous).</span></span> <span data-ttu-id="dde19-112">InboundFileFilter プロパティについての例では、受信処理中に使用されているため方が適切です [その他] ではなく、プロパティに受信を割り当てる。</span><span class="sxs-lookup"><span data-stu-id="dde19-112">As to the InboundFileFilter property, since it is used during the inbound handling within the example, it is more appropriate to assign Inbound to the property, rather than Miscellaneous.</span></span> <span data-ttu-id="dde19-113">エコー アダプターのカスタム プロパティの完全な分類を次に示します。</span><span class="sxs-lookup"><span data-stu-id="dde19-113">Here is the complete custom property categorization for the echo adapter.</span></span>  
  
|<span data-ttu-id="dde19-114">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="dde19-114">**Property**</span></span>|<span data-ttu-id="dde19-115">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="dde19-115">**Category**</span></span>|  
|------------------|------------------|  
|<span data-ttu-id="dde19-116">InboundFileFilter</span><span class="sxs-lookup"><span data-stu-id="dde19-116">InboundFileFilter</span></span>|<span data-ttu-id="dde19-117">受信</span><span class="sxs-lookup"><span data-stu-id="dde19-117">Inbound</span></span>|  
|<span data-ttu-id="dde19-118">InboundFileSystemWatcherFolder</span><span class="sxs-lookup"><span data-stu-id="dde19-118">InboundFileSystemWatcherFolder</span></span>|<span data-ttu-id="dde19-119">受信</span><span class="sxs-lookup"><span data-stu-id="dde19-119">Inbound</span></span>|  
|<span data-ttu-id="dde19-120">Count</span><span class="sxs-lookup"><span data-stu-id="dde19-120">Count</span></span>|<span data-ttu-id="dde19-121">その他</span><span class="sxs-lookup"><span data-stu-id="dde19-121">Misc</span></span>|  
|<span data-ttu-id="dde19-122">EnableConnectionPooling</span><span class="sxs-lookup"><span data-stu-id="dde19-122">EnableConnectionPooling</span></span>|<span data-ttu-id="dde19-123">その他</span><span class="sxs-lookup"><span data-stu-id="dde19-123">Misc</span></span>|  
|<span data-ttu-id="dde19-124">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="dde19-124">Application</span></span>|<span data-ttu-id="dde19-125">接続</span><span class="sxs-lookup"><span data-stu-id="dde19-125">Connection</span></span>|  
|<span data-ttu-id="dde19-126">EnableAuthentication</span><span class="sxs-lookup"><span data-stu-id="dde19-126">EnableAuthentication</span></span>|<span data-ttu-id="dde19-127">接続</span><span class="sxs-lookup"><span data-stu-id="dde19-127">Connection</span></span>|  
|<span data-ttu-id="dde19-128">hostname</span><span class="sxs-lookup"><span data-stu-id="dde19-128">Hostname</span></span>|<span data-ttu-id="dde19-129">接続</span><span class="sxs-lookup"><span data-stu-id="dde19-129">Connection</span></span>|  
|<span data-ttu-id="dde19-130">EchoInUpperCase</span><span class="sxs-lookup"><span data-stu-id="dde19-130">EchoInUpperCase</span></span>|<span data-ttu-id="dde19-131">Format</span><span class="sxs-lookup"><span data-stu-id="dde19-131">Format</span></span>|  
  
 <span data-ttu-id="dde19-132">Dispose メソッドの変更もこれらの変更だけでなく**EchoAdapterHandlerBase**です。</span><span class="sxs-lookup"><span data-stu-id="dde19-132">In addition to those changes, you also modify the Dispose method of **EchoAdapterHandlerBase**.</span></span>  
  
 <span data-ttu-id="dde19-133">エコー アダプターによって公開されているアダプターのプロパティは、アダプターのプロパティ セクションを参照してください、[チュートリアル 1: エコー アダプターを開発](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="dde19-133">For the adapter properties exposed by the echo adapter, see the adapter properties section of the [Tutorial 1: Develop the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="dde19-134">前提条件</span><span class="sxs-lookup"><span data-stu-id="dde19-134">Prerequisites</span></span>  
 <span data-ttu-id="dde19-135">この手順を開始する前に行う必要があります[手順 1: エコー アダプター プロジェクトを作成する WCF LOB アダプター開発ウィザードを使用して](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-1-use-the-wcf-lob-adapter-development-wizard-to-create-the-echo-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="dde19-135">Before you begin this step, you must complete [Step 1: Use the WCF LOB Adapter Development Wizard to Create the Echo Adapter Project](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-1-use-the-wcf-lob-adapter-development-wizard-to-create-the-echo-adapter.md).</span></span> <span data-ttu-id="dde19-136">必要がありますもよく理解すると、`System.ServiceModel.Configuration.BindingElementExtensionElement`と`System.ServiceModel.Configuration.StandardBindingElement`クラスです。</span><span class="sxs-lookup"><span data-stu-id="dde19-136">You should also be familiar with the `System.ServiceModel.Configuration.BindingElementExtensionElement` and `System.ServiceModel.Configuration.StandardBindingElement` classes.</span></span>  
  
## <a name="update-the-echoadapterhandlerbase-dispose-method"></a><span data-ttu-id="dde19-137">Update EchoAdapterHandlerBase Dispose メソッド</span><span class="sxs-lookup"><span data-stu-id="dde19-137">Update the EchoAdapterHandlerBase Dispose method</span></span>  
  
1.  <span data-ttu-id="dde19-138">**ソリューション エクスプ ローラー**をダブルクリックして、 **EchoAdapterHandlerBase.cs**ファイル。</span><span class="sxs-lookup"><span data-stu-id="dde19-138">In **Solution Explorer**, double-click the **EchoAdapterHandlerBase.cs** file.</span></span>  
  
2.  <span data-ttu-id="dde19-139">次のステートメントを削除、 **Dispose**メソッド。</span><span class="sxs-lookup"><span data-stu-id="dde19-139">Remove the following statement from the **Dispose** method:</span></span>  
  
    ```csharp  
    throw new NotImplementedException("The method or operation is not implemented.");  
    ```  
  
     <span data-ttu-id="dde19-140">変更後のメソッドは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="dde19-140">The revised method should look similar to the following:</span></span>  
  
    ```csharp  
    protected virtual void Dispose(bool disposing)  
    {  
       //  
       //TODO: Implement Dispose. Override this method in respective Handler classes  
       //  
    }  
    ```  
  
## <a name="update-the-adapter-properties-class"></a><span data-ttu-id="dde19-141">更新アダプター プロパティ クラス</span><span class="sxs-lookup"><span data-stu-id="dde19-141">Update the Adapter properties class</span></span>  
  
1.  <span data-ttu-id="dde19-142">**ソリューション エクスプ ローラー**をダブルクリックして、 **EchoAdapterBindingElement.cs**ファイル。</span><span class="sxs-lookup"><span data-stu-id="dde19-142">In **Solution Explorer**, double-click the **EchoAdapterBindingElement.cs** file.</span></span>  
  
2.  <span data-ttu-id="dde19-143">Visual Studio エディターで、展開、**カスタム生成プロパティ**領域。</span><span class="sxs-lookup"><span data-stu-id="dde19-143">In the Visual Studio editor, expand the **Custom Generated Properties** region.</span></span>  
  
3.  <span data-ttu-id="dde19-144">割り当てる、**その他**カテゴリを**カウント**プロパティの先頭に次の 1 つのステートメントを追加、**カウント**実装します。</span><span class="sxs-lookup"><span data-stu-id="dde19-144">To assign the **Misc** category to the **Count** property, add the following single statement to the beginning of the **Count** implementation.</span></span>  
  
    ```csharp  
    [System.ComponentModel.Category("")]  
    ```  
  
     <span data-ttu-id="dde19-145">**カウント**実装が次と一致する必要がありますようになりました。</span><span class="sxs-lookup"><span data-stu-id="dde19-145">The **Count** implementation should now match the following:</span></span>  
  
    ```csharp  
    [System.ComponentModel.Category("")]  
    [System.Configuration.ConfigurationProperty("count", DefaultValue = 5)]  
    public int Count  
    {  
        get  
        {  
            return ((int)(base["Count"]));  
        }  
        set  
        {  
            base["Count"] = value;  
        }  
    }  
    ```  
  
4.  <span data-ttu-id="dde19-146">割り当てる、**その他**カテゴリ、 **EnableConnectionPooling**プロパティの先頭に次の 1 つのステートメントを追加、 **EnableConnectionPooling**実装です。</span><span class="sxs-lookup"><span data-stu-id="dde19-146">To assign the **Misc** category to the **EnableConnectionPooling** property, add the following single statement to the beginning of the **EnableConnectionPooling** implementation.</span></span>  
  
    ```csharp  
    [System.ComponentModel.Category("")]  
    ```  
  
5.  <span data-ttu-id="dde19-147">割り当てる、**受信**カテゴリ、 **InboundFileFilter**プロパティの先頭に次の 1 つのステートメントを追加、 **InboundFileFilter**実装します。</span><span class="sxs-lookup"><span data-stu-id="dde19-147">To assign the **Inbound** category to the **InboundFileFilter** property, add the following single statement to the beginning of the **InboundFileFilter** implementation.</span></span>  
  
    ```csharp  
    [System.ComponentModel.Category("Inbound")]  
    ```  
  
6.  <span data-ttu-id="dde19-148">割り当てる、**受信**categoryto **inboundFleSystemWatcherFolder**プロパティの先頭に次の 1 つのステートメントを追加、 **inboundFleSystemWatcherFolder**実装します。</span><span class="sxs-lookup"><span data-stu-id="dde19-148">To assign the **Inbound** categoryto **inboundFleSystemWatcherFolder** property, add the following single statement to the beginning of the **inboundFleSystemWatcherFolder** implementation.</span></span>  
  
    ```csharp  
    [System.ComponentModel.Category("Inbound")]  
    ```  
  
7.  <span data-ttu-id="dde19-149">内のコードを確認してください、**カスタム生成プロパティ**地域、次の一致します。</span><span class="sxs-lookup"><span data-stu-id="dde19-149">Check to ensure that the code in the **Custom Generated Properties** region matches the following:</span></span>  
  
    ```csharp  
    [System.ComponentModel.Category("")]  
    [System.Configuration.ConfigurationProperty("count", DefaultValue = 5)]  
    public int Count  
    {  
        get  
        {  
            return ((int)(base["Count"]));  
        }  
        set  
        {  
            base["Count"] = value;  
        }  
    }  
  
    [System.ComponentModel.Category("")]  
    [System.Configuration.ConfigurationProperty("enableConnectionPooling", DefaultValue = true)]  
    public bool EnableConnectionPooling  
    {  
        get  
        {  
            return ((bool)(base["EnableConnectionPooling"]));  
        }  
        set  
        {  
            base["EnableConnectionPooling"] = value;  
        }  
    }  
  
    [System.ComponentModel.Category("Inbound")]  
    [System.Configuration.ConfigurationProperty("inboundFileFilter", DefaultValue = "*.txt")]  
    public string InboundFileFilter  
    {  
        get  
        {  
            return ((string)(base["InboundFileFilter"]));  
        }  
        set  
        {  
            base["InboundFileFilter"] = value;  
        }  
    }  
  
    [System.ComponentModel.Category("Inbound")]  
    [System.Configuration.ConfigurationProperty("inboundFileSystemWatcherFolder", DefaultValue = "{InboundFileSystemWatcherFolder}")]  
    public string InboundFileSystemWatcherFolder  
    {  
        get  
        {  
            return ((string)(base["InboundFileSystemWatcherFolder"]));  
        }  
        set  
        {  
            base["InboundFileSystemWatcherFolder"] = value;  
        }  
    }  
  
    #endregion Custom Generated Properties  
    ```  
  
## <a name="update-the-connection-properties"></a><span data-ttu-id="dde19-150">接続プロパティを更新します。</span><span class="sxs-lookup"><span data-stu-id="dde19-150">Update the Connection Properties</span></span>  
  
1.  <span data-ttu-id="dde19-151">**ソリューション エクスプ ローラー**をダブルクリックして、 **EchoAdapterConnectionUri.cs**ファイル。</span><span class="sxs-lookup"><span data-stu-id="dde19-151">In **Solution Explorer**, double-click the **EchoAdapterConnectionUri.cs** file.</span></span>  
  
2.  <span data-ttu-id="dde19-152">Visual Studio エディターで、展開、**カスタム生成プロパティ**領域。</span><span class="sxs-lookup"><span data-stu-id="dde19-152">In the Visual Studio editor, expand the **Custom Generated Properties** region.</span></span>  
  
3.  <span data-ttu-id="dde19-153">割り当てる、**形式**カテゴリ、 **EchoInUpperCase**プロパティの先頭に次の 1 つのステートメントを追加、 **EchoInUpperCase**実装します。</span><span class="sxs-lookup"><span data-stu-id="dde19-153">To assign the **Format** category to the **EchoInUpperCase** property, add the following single statement to the beginning of the **EchoInUpperCase** implementation.</span></span>  
  
    ```csharp  
    [System.ComponentModel.Category("Format")]  
    ```  
  
4.  <span data-ttu-id="dde19-154">割り当てる、**接続**カテゴリを**ホスト名**プロパティの先頭に次の 1 つのステートメントを追加、**ホスト名**実装します。</span><span class="sxs-lookup"><span data-stu-id="dde19-154">To assign the **Connection** category to the **Hostname** property, add the following single statement to the beginning of the **Hostname** implementation.</span></span>  
  
    ```csharp  
    [System.ComponentModel.Category("Connection")]  
    ```  
  
5.  <span data-ttu-id="dde19-155">割り当てる、**接続**カテゴリ、**アプリケーション**プロパティの先頭に次の 1 つのステートメントを追加、**アプリケーション**実装します。</span><span class="sxs-lookup"><span data-stu-id="dde19-155">To assign the **Connection** category to the **Application** property, add the following single statement to the beginning of the **Application** implementation.</span></span>  
  
    ```csharp  
    [System.ComponentModel.Category("Connection")]  
    ```  
  
6.  <span data-ttu-id="dde19-156">割り当てる、**接続**categoryto **EnableAuthentication**プロパティの先頭に次の 1 つのステートメントを追加、 **EnableAuthentication**実装です。</span><span class="sxs-lookup"><span data-stu-id="dde19-156">To assign the **Connection** categoryto **EnableAuthentication** property, add the following single statement to the beginning of the **EnableAuthentication** implementation.</span></span>  
  
    ```csharp  
    [System.ComponentModel.Category("Connection")]  
    ```  
  
7.  <span data-ttu-id="dde19-157">内のコードを確認してください、**カスタム生成プロパティ**地域、次の一致します。</span><span class="sxs-lookup"><span data-stu-id="dde19-157">Check to ensure that the code in the **Custom Generated Properties** region matches the following:</span></span>  
  
    ```csharp  
    #region Custom Generated Properties  
            [System.ComponentModel.Category("Format")]  
            public bool EchoInUpperCase  
            {  
                get  
                {  
                    return this.echoInUpperCase;  
                }  
                set  
                {  
                    this.echoInUpperCase = value;  
                }  
            }  
  
            [System.ComponentModel.Category("Connection")]  
            public string Hostname  
            {  
                get  
                {  
                    return this.hostname;  
                }  
                set  
                {  
                    this.hostname = value;  
                }  
            }  
  
            [System.ComponentModel.Category("Connection")]  
            public string Application  
            {  
                get  
                {  
                    return this.application;  
                }  
                set  
                {  
                    this.application = value;  
                }  
            }  
  
            [System.ComponentModel.Category("Connection")]  
            public bool EnableAuthentication  
            {  
                get  
                {  
                    return this.enableAuthentication;  
                }  
                set  
                {  
                    this.enableAuthentication = value;  
                }  
            }  
            #endregion Custom Generated Properties  
    ```  
  
8.  <span data-ttu-id="dde19-158">Visual Studio から、**ファイル** メニューのをクリックして**すべて保存**です。</span><span class="sxs-lookup"><span data-stu-id="dde19-158">In Visual Studio, from the **File** menu, click **Save All**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dde19-159">これで作業が保存されました。</span><span class="sxs-lookup"><span data-stu-id="dde19-159">You saved your work.</span></span> <span data-ttu-id="dde19-160">安全にこの時点で Visual Studio を終了したり、次の手順に進みます[手順 3: エコー アダプターの接続を実装](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-implement-the-connection-for-the-echo-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="dde19-160">You can safely close Visual Studio at this time or go to the next step, [Step 3: Implement the Connection for the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-implement-the-connection-for-the-echo-adapter.md).</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="dde19-161">でしただけは何ですか。</span><span class="sxs-lookup"><span data-stu-id="dde19-161">What Did I Just Do?</span></span>  
 <span data-ttu-id="dde19-162">エコー アダプターによって公開される各アダプターと接続プロパティをカテゴリに分類するクラスが更新されました。</span><span class="sxs-lookup"><span data-stu-id="dde19-162">You just updated classes to assign a category to each adapter and connection property exposed by the echo adapter.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="dde19-163">次の手順</span><span class="sxs-lookup"><span data-stu-id="dde19-163">Next Steps</span></span>  
 <span data-ttu-id="dde19-164">接続、メタデータの参照、検索、および機能、および送信メッセージ交換の解決を実装するとします。</span><span class="sxs-lookup"><span data-stu-id="dde19-164">You implement connection, metadata browsing, searching, and resolving capabilities, and the outbound message exchange.</span></span> <span data-ttu-id="dde19-165">最後に、ビルドおよび展開するエコー アダプター。</span><span class="sxs-lookup"><span data-stu-id="dde19-165">Lastly, you build and deploy the echo adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dde19-166">参照</span><span class="sxs-lookup"><span data-stu-id="dde19-166">See Also</span></span>  
 <span data-ttu-id="dde19-167">[手順 3: エコー アダプターの接続を実装します。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-implement-the-connection-for-the-echo-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="dde19-167">[Step 3: Implement the Connection for the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-implement-the-connection-for-the-echo-adapter.md) </span></span>  
 [<span data-ttu-id="dde19-168">チュートリアル 1: エコー アダプターを開発します。</span><span class="sxs-lookup"><span data-stu-id="dde19-168">Tutorial 1: Develop the Echo Adapter</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)