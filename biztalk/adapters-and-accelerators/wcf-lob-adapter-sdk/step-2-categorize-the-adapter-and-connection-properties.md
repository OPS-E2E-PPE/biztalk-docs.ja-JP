---
title: 手順 2:アダプターおよび接続のプロパティを分類 |Microsoft Docs
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
ms.openlocfilehash: 3d0d618d2e02e04b69e054c473b4a8b817cb52b1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65363340"
---
# <a name="step-2-categorize-the-adapter-and-connection-properties"></a><span data-ttu-id="de221-102">手順 2:アダプターと接続のプロパティを分類します。</span><span class="sxs-lookup"><span data-stu-id="de221-102">Step 2: Categorize the Adapter and Connection Properties</span></span>
<span data-ttu-id="de221-103">![手順 2 の 9](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-2of9.gif "Step_2of9")</span><span class="sxs-lookup"><span data-stu-id="de221-103">![Step 2 of 9](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-2of9.gif "Step_2of9")</span></span>  
  
 <span data-ttu-id="de221-104">**所要時間:** 30 分</span><span class="sxs-lookup"><span data-stu-id="de221-104">**Time to complete:** 30 minutes</span></span>  
  
 <span data-ttu-id="de221-105">この手順で更新する、 **EchoAdapterBindingElement**と**EchoAdapterBindingElementExtensionElement**アダプターと接続のプロパティをカテゴリに分類するためのクラス。</span><span class="sxs-lookup"><span data-stu-id="de221-105">In this step, you update the **EchoAdapterBindingElement** and **EchoAdapterBindingElementExtensionElement** classes to assign a category to your adapter and connection properties.</span></span> <span data-ttu-id="de221-106">これにより、プロパティは論理的にグループ化のカテゴリによって、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]と[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]ツール。</span><span class="sxs-lookup"><span data-stu-id="de221-106">By doing so, properties are logically grouped by category in the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] and [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] tools.</span></span> <span data-ttu-id="de221-107">たとえば、する場合は、**アプリケーション**、 **EnableAuthentication**と**ホスト名**プロパティの下に表示、**接続**カテゴリの下に示すように、アプリケーション、EnableAuthentication、およびホスト名のプロパティに接続のカテゴリを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="de221-107">For example, if you want the **Application**, **EnableAuthentication**, and **Hostname** properties to appear under the **Connection** category as shown below, you need to assign the Connection category to each of the Application, EnableAuthentication, and Hostname properties.</span></span>  
  
 <span data-ttu-id="de221-108">![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/c7c0c013-6651-4c32-9f8b-b546a68a0267.gif "c7c0c013-6651-4c32-9f8b-b546a68a0267")</span><span class="sxs-lookup"><span data-stu-id="de221-108">![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/c7c0c013-6651-4c32-9f8b-b546a68a0267.gif "c7c0c013-6651-4c32-9f8b-b546a68a0267")</span></span>  
  
 <span data-ttu-id="de221-109">同様に、する場合は、 **InboundFileFilter**と**InboundFleSystemWatcherFolder**下に表示されるプロパティ、**受信**カテゴリの下に示すようにする必要があります各に受信のカテゴリを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="de221-109">Similarly, if you want the **InboundFileFilter** and **InboundFleSystemWatcherFolder** properties to appear under the **Inbound** category as shown below, you need to assign the Inbound category to each.</span></span> <span data-ttu-id="de221-110">場合は**カウント**と**EnableConnectionPooling**の下に表示、 **Misc**カテゴリで、それぞれに、その他のカテゴリを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="de221-110">If you want **Count** and **EnableConnectionPooling** to appear under the **Misc** category, you need to assign the Misc category to each.</span></span>  
  
 <span data-ttu-id="de221-111">![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/2acb7677-8b50-4e45-96a3-42d0e2011f19.gif "2acb7677-8b50-4e45-96a3-42d0e2011f19")</span><span class="sxs-lookup"><span data-stu-id="de221-111">![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/2acb7677-8b50-4e45-96a3-42d0e2011f19.gif "2acb7677-8b50-4e45-96a3-42d0e2011f19")</span></span>  
  
 <span data-ttu-id="de221-112">選択した任意のカテゴリ名を持つプロパティを割り当てることができることに留意してください。</span><span class="sxs-lookup"><span data-stu-id="de221-112">Keep in mind that you can assign a property with any category name you choose.</span></span> <span data-ttu-id="de221-113">この例で EnableConnnectionPooling プロパティが、他のカテゴリに属さないためここに分類その他 (その他)。</span><span class="sxs-lookup"><span data-stu-id="de221-113">In this example, since the EnableConnnectionPooling property does not belong to any other categories, we categorize it as Misc (Miscellaneous).</span></span> <span data-ttu-id="de221-114">InboundFileFilter プロパティについて内での例では、受信処理中に使用されるため方が適切です (その他) ではなく、プロパティに受信を割り当てる。</span><span class="sxs-lookup"><span data-stu-id="de221-114">As to the InboundFileFilter property, since it is used during the inbound handling within the example, it is more appropriate to assign Inbound to the property, rather than Miscellaneous.</span></span> <span data-ttu-id="de221-115">エコー アダプターのカスタム プロパティの完全な分類を次に示します。</span><span class="sxs-lookup"><span data-stu-id="de221-115">Here is the complete custom property categorization for the echo adapter.</span></span>  
  
|<span data-ttu-id="de221-116">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="de221-116">**Property**</span></span>|<span data-ttu-id="de221-117">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="de221-117">**Category**</span></span>|  
|------------------|------------------|  
|<span data-ttu-id="de221-118">InboundFileFilter</span><span class="sxs-lookup"><span data-stu-id="de221-118">InboundFileFilter</span></span>|<span data-ttu-id="de221-119">受信</span><span class="sxs-lookup"><span data-stu-id="de221-119">Inbound</span></span>|  
|<span data-ttu-id="de221-120">InboundFileSystemWatcherFolder</span><span class="sxs-lookup"><span data-stu-id="de221-120">InboundFileSystemWatcherFolder</span></span>|<span data-ttu-id="de221-121">受信</span><span class="sxs-lookup"><span data-stu-id="de221-121">Inbound</span></span>|  
|<span data-ttu-id="de221-122">Count</span><span class="sxs-lookup"><span data-stu-id="de221-122">Count</span></span>|<span data-ttu-id="de221-123">その他</span><span class="sxs-lookup"><span data-stu-id="de221-123">Misc</span></span>|  
|<span data-ttu-id="de221-124">EnableConnectionPooling</span><span class="sxs-lookup"><span data-stu-id="de221-124">EnableConnectionPooling</span></span>|<span data-ttu-id="de221-125">その他</span><span class="sxs-lookup"><span data-stu-id="de221-125">Misc</span></span>|  
|<span data-ttu-id="de221-126">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="de221-126">Application</span></span>|<span data-ttu-id="de221-127">接続</span><span class="sxs-lookup"><span data-stu-id="de221-127">Connection</span></span>|  
|<span data-ttu-id="de221-128">EnableAuthentication</span><span class="sxs-lookup"><span data-stu-id="de221-128">EnableAuthentication</span></span>|<span data-ttu-id="de221-129">接続</span><span class="sxs-lookup"><span data-stu-id="de221-129">Connection</span></span>|  
|<span data-ttu-id="de221-130">hostname</span><span class="sxs-lookup"><span data-stu-id="de221-130">Hostname</span></span>|<span data-ttu-id="de221-131">接続</span><span class="sxs-lookup"><span data-stu-id="de221-131">Connection</span></span>|  
|<span data-ttu-id="de221-132">EchoInUpperCase</span><span class="sxs-lookup"><span data-stu-id="de221-132">EchoInUpperCase</span></span>|<span data-ttu-id="de221-133">形式</span><span class="sxs-lookup"><span data-stu-id="de221-133">Format</span></span>|  
  
 <span data-ttu-id="de221-134">Dispose メソッドの変更もこれらの変更だけでなく**EchoAdapterHandlerBase**します。</span><span class="sxs-lookup"><span data-stu-id="de221-134">In addition to those changes, you also modify the Dispose method of **EchoAdapterHandlerBase**.</span></span>  
  
 <span data-ttu-id="de221-135">エコー アダプターによって公開されているアダプターのプロパティのアダプターのプロパティ セクションを参照してください、[チュートリアル 1。エコー アダプターを開発](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="de221-135">For the adapter properties exposed by the echo adapter, see the adapter properties section of the [Tutorial 1: Develop the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="de221-136">前提条件</span><span class="sxs-lookup"><span data-stu-id="de221-136">Prerequisites</span></span>  
 <span data-ttu-id="de221-137">この手順を開始する前に行う必要があります[手順 1。WCF LOB アダプター開発ウィザードを使用してエコー アダプター プロジェクトを作成する](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-1-use-the-wcf-lob-adapter-development-wizard-to-create-the-echo-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="de221-137">Before you begin this step, you must complete [Step 1: Use the WCF LOB Adapter Development Wizard to Create the Echo Adapter Project](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-1-use-the-wcf-lob-adapter-development-wizard-to-create-the-echo-adapter.md).</span></span> <span data-ttu-id="de221-138">知識も必要、`System.ServiceModel.Configuration.BindingElementExtensionElement`と`System.ServiceModel.Configuration.StandardBindingElement`クラス。</span><span class="sxs-lookup"><span data-stu-id="de221-138">You should also be familiar with the `System.ServiceModel.Configuration.BindingElementExtensionElement` and `System.ServiceModel.Configuration.StandardBindingElement` classes.</span></span>  
  
## <a name="update-the-echoadapterhandlerbase-dispose-method"></a><span data-ttu-id="de221-139">EchoAdapterHandlerBase Dispose メソッドを更新します。</span><span class="sxs-lookup"><span data-stu-id="de221-139">Update the EchoAdapterHandlerBase Dispose method</span></span>  
  
1.  <span data-ttu-id="de221-140">**ソリューション エクスプ ローラー**、ダブルクリックして、 **EchoAdapterHandlerBase.cs**ファイル。</span><span class="sxs-lookup"><span data-stu-id="de221-140">In **Solution Explorer**, double-click the **EchoAdapterHandlerBase.cs** file.</span></span>  
  
2.  <span data-ttu-id="de221-141">次のステートメントを削除、 **Dispose**メソッド。</span><span class="sxs-lookup"><span data-stu-id="de221-141">Remove the following statement from the **Dispose** method:</span></span>  
  
    ```csharp  
    throw new NotImplementedException("The method or operation is not implemented.");  
    ```  
  
     <span data-ttu-id="de221-142">変更後のメソッドは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="de221-142">The revised method should look similar to the following:</span></span>  
  
    ```csharp  
    protected virtual void Dispose(bool disposing)  
    {  
       //  
       //TODO: Implement Dispose. Override this method in respective Handler classes  
       //  
    }  
    ```  
  
## <a name="update-the-adapter-properties-class"></a><span data-ttu-id="de221-143">更新アダプター プロパティ クラス</span><span class="sxs-lookup"><span data-stu-id="de221-143">Update the Adapter properties class</span></span>  
  
1.  <span data-ttu-id="de221-144">**ソリューション エクスプ ローラー**、ダブルクリックして、 **EchoAdapterBindingElement.cs**ファイル。</span><span class="sxs-lookup"><span data-stu-id="de221-144">In **Solution Explorer**, double-click the **EchoAdapterBindingElement.cs** file.</span></span>  
  
2.  <span data-ttu-id="de221-145">Visual Studio エディターで、展開、**カスタム生成プロパティ**リージョン。</span><span class="sxs-lookup"><span data-stu-id="de221-145">In the Visual Studio editor, expand the **Custom Generated Properties** region.</span></span>  
  
3.  <span data-ttu-id="de221-146">割り当てる、**その他**カテゴリを**カウント**プロパティの先頭に次の 1 つのステートメントを追加、**数**実装。</span><span class="sxs-lookup"><span data-stu-id="de221-146">To assign the **Misc** category to the **Count** property, add the following single statement to the beginning of the **Count** implementation.</span></span>  
  
    ```csharp  
    [System.ComponentModel.Category("")]  
    ```  
  
     <span data-ttu-id="de221-147">**カウント**実装、次に一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="de221-147">The **Count** implementation should now match the following:</span></span>  
  
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
  
4.  <span data-ttu-id="de221-148">割り当てる、**その他**カテゴリ、 **EnableConnectionPooling**プロパティの先頭に次の 1 つのステートメントを追加、 **EnableConnectionPooling**実装です。</span><span class="sxs-lookup"><span data-stu-id="de221-148">To assign the **Misc** category to the **EnableConnectionPooling** property, add the following single statement to the beginning of the **EnableConnectionPooling** implementation.</span></span>  
  
    ```csharp  
    [System.ComponentModel.Category("")]  
    ```  
  
5.  <span data-ttu-id="de221-149">割り当てる、**受信**カテゴリ、 **InboundFileFilter**プロパティの先頭に次の 1 つのステートメントを追加、 **InboundFileFilter**実装。</span><span class="sxs-lookup"><span data-stu-id="de221-149">To assign the **Inbound** category to the **InboundFileFilter** property, add the following single statement to the beginning of the **InboundFileFilter** implementation.</span></span>  
  
    ```csharp  
    [System.ComponentModel.Category("Inbound")]  
    ```  
  
6.  <span data-ttu-id="de221-150">割り当てる、**受信**categoryto **inboundFleSystemWatcherFolder**プロパティの先頭に次の 1 つのステートメントを追加、 **inboundFleSystemWatcherFolder**実装します。</span><span class="sxs-lookup"><span data-stu-id="de221-150">To assign the **Inbound** categoryto **inboundFleSystemWatcherFolder** property, add the following single statement to the beginning of the **inboundFleSystemWatcherFolder** implementation.</span></span>  
  
    ```csharp  
    [System.ComponentModel.Category("Inbound")]  
    ```  
  
7.  <span data-ttu-id="de221-151">コードでは、ことを確認、**カスタム生成プロパティ**リージョンが次と一致します。</span><span class="sxs-lookup"><span data-stu-id="de221-151">Check to ensure that the code in the **Custom Generated Properties** region matches the following:</span></span>  
  
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
  
## <a name="update-the-connection-properties"></a><span data-ttu-id="de221-152">接続プロパティを更新します。</span><span class="sxs-lookup"><span data-stu-id="de221-152">Update the Connection Properties</span></span>  
  
1.  <span data-ttu-id="de221-153">**ソリューション エクスプ ローラー**、ダブルクリックして、 **EchoAdapterConnectionUri.cs**ファイル。</span><span class="sxs-lookup"><span data-stu-id="de221-153">In **Solution Explorer**, double-click the **EchoAdapterConnectionUri.cs** file.</span></span>  
  
2.  <span data-ttu-id="de221-154">Visual Studio エディターで、展開、**カスタム生成プロパティ**リージョン。</span><span class="sxs-lookup"><span data-stu-id="de221-154">In the Visual Studio editor, expand the **Custom Generated Properties** region.</span></span>  
  
3.  <span data-ttu-id="de221-155">割り当てる、**形式**カテゴリ、 **EchoInUpperCase**プロパティの先頭に次の 1 つのステートメントを追加、 **EchoInUpperCase**実装。</span><span class="sxs-lookup"><span data-stu-id="de221-155">To assign the **Format** category to the **EchoInUpperCase** property, add the following single statement to the beginning of the **EchoInUpperCase** implementation.</span></span>  
  
    ```csharp  
    [System.ComponentModel.Category("Format")]  
    ```  
  
4.  <span data-ttu-id="de221-156">割り当てる、**接続**カテゴリ、**ホスト名**プロパティの先頭に次の 1 つのステートメントを追加、**ホスト名**実装。</span><span class="sxs-lookup"><span data-stu-id="de221-156">To assign the **Connection** category to the **Hostname** property, add the following single statement to the beginning of the **Hostname** implementation.</span></span>  
  
    ```csharp  
    [System.ComponentModel.Category("Connection")]  
    ```  
  
5.  <span data-ttu-id="de221-157">割り当てる、**接続**カテゴリ、**アプリケーション**プロパティの先頭に次の 1 つのステートメントを追加、**アプリケーション**実装。</span><span class="sxs-lookup"><span data-stu-id="de221-157">To assign the **Connection** category to the **Application** property, add the following single statement to the beginning of the **Application** implementation.</span></span>  
  
    ```csharp  
    [System.ComponentModel.Category("Connection")]  
    ```  
  
6.  <span data-ttu-id="de221-158">割り当てる、**接続**categoryto **EnableAuthentication**プロパティの先頭に次の 1 つのステートメントを追加、 **EnableAuthentication**実装です。</span><span class="sxs-lookup"><span data-stu-id="de221-158">To assign the **Connection** categoryto **EnableAuthentication** property, add the following single statement to the beginning of the **EnableAuthentication** implementation.</span></span>  
  
    ```csharp  
    [System.ComponentModel.Category("Connection")]  
    ```  
  
7.  <span data-ttu-id="de221-159">コードでは、ことを確認、**カスタム生成プロパティ**リージョンが次と一致します。</span><span class="sxs-lookup"><span data-stu-id="de221-159">Check to ensure that the code in the **Custom Generated Properties** region matches the following:</span></span>  
  
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
  
8.  <span data-ttu-id="de221-160">Visual Studio から、**ファイル** メニューのをクリックして**すべて保存**します。</span><span class="sxs-lookup"><span data-stu-id="de221-160">In Visual Studio, from the **File** menu, click **Save All**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="de221-161">これで作業が保存されました。</span><span class="sxs-lookup"><span data-stu-id="de221-161">You saved your work.</span></span> <span data-ttu-id="de221-162">安全にこの時点で Visual Studio を閉じて、次の手順に進むまたは[手順 3。エコー アダプターの接続を実装](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-implement-the-connection-for-the-echo-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="de221-162">You can safely close Visual Studio at this time or go to the next step, [Step 3: Implement the Connection for the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-implement-the-connection-for-the-echo-adapter.md).</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="de221-163">でしただけ何か。</span><span class="sxs-lookup"><span data-stu-id="de221-163">What Did I Just Do?</span></span>  
 <span data-ttu-id="de221-164">エコー アダプターによって公開される各アダプターと接続のプロパティをカテゴリに分類するためのクラスが更新されました。</span><span class="sxs-lookup"><span data-stu-id="de221-164">You just updated classes to assign a category to each adapter and connection property exposed by the echo adapter.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="de221-165">次の手順</span><span class="sxs-lookup"><span data-stu-id="de221-165">Next Steps</span></span>  
 <span data-ttu-id="de221-166">接続、メタデータの参照、検索、および機能、および送信のメッセージ交換の解決を実装します。</span><span class="sxs-lookup"><span data-stu-id="de221-166">You implement connection, metadata browsing, searching, and resolving capabilities, and the outbound message exchange.</span></span> <span data-ttu-id="de221-167">最後に、ビルドし、エコー アダプターを展開します。</span><span class="sxs-lookup"><span data-stu-id="de221-167">Lastly, you build and deploy the echo adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de221-168">参照</span><span class="sxs-lookup"><span data-stu-id="de221-168">See Also</span></span>  
 <span data-ttu-id="de221-169">[ステップ 3:エコー アダプターの接続を実装します。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-implement-the-connection-for-the-echo-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="de221-169">[Step 3: Implement the Connection for the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-implement-the-connection-for-the-echo-adapter.md) </span></span>  
 [<span data-ttu-id="de221-170">チュートリアル 1:エコー アダプターを開発する</span><span class="sxs-lookup"><span data-stu-id="de221-170">Tutorial 1: Develop the Echo Adapter</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)