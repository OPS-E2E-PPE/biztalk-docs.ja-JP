---
title: Oracle データベース アダプターの Oracle クライアントの構成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- net service name
- tnsnames.ora
- configuring, the Oracle client
- connect descriptor
- Oracle client, configuring
- Oracle Net Configuration Assistant
- Oracle Net Configuration Assistant, using the
ms.assetid: 2d4c0f20-b3a6-453f-a9b3-65fd5a38c020
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 209d5603a9f8ff8c09185093efb976afb6432d65
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214114"
---
# <a name="configure-the-oracle-client-for-the-oracle-database-adapter"></a><span data-ttu-id="4f496-102">Oracle データベース アダプターの Oracle クライアントを構成します。</span><span class="sxs-lookup"><span data-stu-id="4f496-102">Configure the Oracle Client for the Oracle Database adapter</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="4f496-103">ここでは、Oracle データベースへの接続に tnsnames.ora を使用している場合にのみ該当します。</span><span class="sxs-lookup"><span data-stu-id="4f496-103">This topic is relevant only if you are using tnsnames.ora to connect to the Oracle database.</span></span>  
  
 <span data-ttu-id="4f496-104">[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]お使いのコンピューターにインストールされている Oracle クライアントを使用して Oracle データベースに接続します。</span><span class="sxs-lookup"><span data-stu-id="4f496-104">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] connects to the Oracle database through the Oracle client installed on your computer.</span></span> <span data-ttu-id="4f496-105">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Net サービス名を渡します Oracle データベースへの接続を確立するために Oracle クライアントへの接続 URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="4f496-105">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] passes the net service name that you specify in the connection URI to the Oracle client to establish a connection to the Oracle database.</span></span> <span data-ttu-id="4f496-106">Net サービス名は、Oracle クライアントが、ターゲットの Oracle データベースのサービスの接続情報の取得に使用するエイリアスです。</span><span class="sxs-lookup"><span data-stu-id="4f496-106">The net service name is an alias that the Oracle client uses to acquire connection information for the target Oracle database service.</span></span>  
  
 <span data-ttu-id="4f496-107">Oracle クライアントは、名前付け方法に従って、net サービス名を使用して構成されていることを解決します。</span><span class="sxs-lookup"><span data-stu-id="4f496-107">The Oracle client resolves the net service name according to the naming method that it is configured to use.</span></span> <span data-ttu-id="4f496-108">使用する Oracle Net Configuration Assistant、Oracle クライアントによって使用される名前付け方法を構成します。</span><span class="sxs-lookup"><span data-stu-id="4f496-108">You use the Oracle Net Configuration Assistant to configure the naming methods to be used by the Oracle client.</span></span> <span data-ttu-id="4f496-109">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle データベースに接続するため、ローカルの名前付けのメソッドをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="4f496-109">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] supports the Local Naming method for connecting to the Oracle database.</span></span> <span data-ttu-id="4f496-110">このメソッドは、net サービス名を解決するのには、ローカル ファイル、tnsnames.ora を使用します。</span><span class="sxs-lookup"><span data-stu-id="4f496-110">This method uses a local file, tnsnames.ora, to resolve the net service name.</span></span>  
  
 <span data-ttu-id="4f496-111">Tnsnames.ora ファイルは、net サービス名を Oracle クライアントが特定の Oracle データベース service (インスタンス) への接続を確立するために必要な情報を含む記述子の接続を関連付けます。</span><span class="sxs-lookup"><span data-stu-id="4f496-111">The tnsnames.ora file associates net service names with connect descriptors that contain the information the Oracle client needs to establish a connection to a specific Oracle database service (instance).</span></span> <span data-ttu-id="4f496-112">Tnsnames.ora からサンプルのエントリを次に示します。</span><span class="sxs-lookup"><span data-stu-id="4f496-112">The following is a sample entry from tnsnames.ora.</span></span>  
  
```  
ADAPTER =  
  (DESCRIPTION =  
    (ADDRESS_LIST =  
      (ADDRESS = (PROTOCOL = TCP)(HOST = yourOracleServer)(PORT = 1521))  
    )  
    (CONNECT_DATA =  
      (SERVICE_NAME = yourOracleDatabaseServiceName)  
    )  
  )  
```  
  
 <span data-ttu-id="4f496-113">このサンプルのエントリでは、アダプターは、net サービス名です。</span><span class="sxs-lookup"><span data-stu-id="4f496-113">In this sample entry, ADAPTER is the net service name.</span></span> <span data-ttu-id="4f496-114">接続記述子は、アドレス情報と、サービスのサービス名、Oracle データベース アダプターに関連付けられているを指定します。</span><span class="sxs-lookup"><span data-stu-id="4f496-114">The connect descriptor specifies address information and the service name of the Oracle database service associated with ADAPTER.</span></span> <span data-ttu-id="4f496-115">Oracle Net Configuration Assistant を使用して、作成 tnsnames.ora で net サービス名を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="4f496-115">You can use the Oracle Net Configuration Assistant to create and configure net service names in tnsnames.ora.</span></span> <span data-ttu-id="4f496-116">Net サービス名を構成した後は、次の例のように接続 URI で指定できます。</span><span class="sxs-lookup"><span data-stu-id="4f496-116">After you have configured the net service name, you can specify it in a connection URI as in the following example.</span></span>  
  
```  
oracledb://ADAPTER  
```  
  
 <span data-ttu-id="4f496-117">Oracle Net Configuration Assistant を使用して tnsnames.ora についての詳細については、Oracle データベース Net Services 管理者ガイド 』 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f496-117">For more information about using the Oracle Net Configuration Assistant and about tnsnames.ora, see the Oracle Database Net Services Administrator's Guide.</span></span> <span data-ttu-id="4f496-118">特定のインストールの構成の詳細についてデータベース管理者に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="4f496-118">Consult your database administrator about configuration details for your specific installation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f496-119">参照</span><span class="sxs-lookup"><span data-stu-id="4f496-119">See Also</span></span>  
[<span data-ttu-id="4f496-120">Oracle データベースへの接続を作成します。</span><span class="sxs-lookup"><span data-stu-id="4f496-120">Create a connection to the Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/create-a-connection-to-the-oracle-database.md)