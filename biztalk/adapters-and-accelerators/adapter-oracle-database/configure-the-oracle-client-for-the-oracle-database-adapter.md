---
title: Oracle データベース アダプターの Oracle クライアントの構成 |Microsoft Docs
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
ms.openlocfilehash: 8a2186f4ea5400d01f477d0ab98c282e37e32d60
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376703"
---
# <a name="configure-the-oracle-client-for-the-oracle-database-adapter"></a><span data-ttu-id="05964-102">Oracle データベース アダプターの Oracle クライアントを構成します。</span><span class="sxs-lookup"><span data-stu-id="05964-102">Configure the Oracle Client for the Oracle Database adapter</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="05964-103">このトピックでは、Oracle データベースへの接続に tnsnames.ora を使用している場合にのみ該当します。</span><span class="sxs-lookup"><span data-stu-id="05964-103">This topic is relevant only if you are using tnsnames.ora to connect to the Oracle database.</span></span>  
  
 <span data-ttu-id="05964-104">[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]はコンピューターにインストールされている Oracle クライアントを使用して Oracle データベースに接続します。</span><span class="sxs-lookup"><span data-stu-id="05964-104">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] connects to the Oracle database through the Oracle client installed on your computer.</span></span> <span data-ttu-id="05964-105">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Net サービス名を渡します Oracle データベースへの接続を確立するために Oracle クライアントへの接続 URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="05964-105">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] passes the net service name that you specify in the connection URI to the Oracle client to establish a connection to the Oracle database.</span></span> <span data-ttu-id="05964-106">Net サービス名は、Oracle クライアントを使用して、ターゲットの Oracle データベースのサービスの接続情報を取得するエイリアスです。</span><span class="sxs-lookup"><span data-stu-id="05964-106">The net service name is an alias that the Oracle client uses to acquire connection information for the target Oracle database service.</span></span>  
  
 <span data-ttu-id="05964-107">Oracle クライアントを使用して構成されている名前付けの方法に従って、net サービス名を解決します。</span><span class="sxs-lookup"><span data-stu-id="05964-107">The Oracle client resolves the net service name according to the naming method that it is configured to use.</span></span> <span data-ttu-id="05964-108">Oracle クライアントで使用される名前付け方法を構成するのに Oracle Net Configuration Assistant を使用します。</span><span class="sxs-lookup"><span data-stu-id="05964-108">You use the Oracle Net Configuration Assistant to configure the naming methods to be used by the Oracle client.</span></span> <span data-ttu-id="05964-109">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle データベースに接続するため、ローカルの名前付けのメソッドをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="05964-109">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] supports the Local Naming method for connecting to the Oracle database.</span></span> <span data-ttu-id="05964-110">このメソッドは、net サービス名を解決するのには、tnsnames.ora、ローカル ファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="05964-110">This method uses a local file, tnsnames.ora, to resolve the net service name.</span></span>  
  
 <span data-ttu-id="05964-111">Tnsnames.ora ファイルは、net サービス名と接続、Oracle クライアントが特定の Oracle database service (インスタンス) への接続を確立するために必要な情報が含まれている記述子を関連付けます。</span><span class="sxs-lookup"><span data-stu-id="05964-111">The tnsnames.ora file associates net service names with connect descriptors that contain the information the Oracle client needs to establish a connection to a specific Oracle database service (instance).</span></span> <span data-ttu-id="05964-112">Tnsnames.ora からエントリの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="05964-112">The following is a sample entry from tnsnames.ora.</span></span>  
  
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
  
 <span data-ttu-id="05964-113">このエントリの例では、アダプターは、net サービス名です。</span><span class="sxs-lookup"><span data-stu-id="05964-113">In this sample entry, ADAPTER is the net service name.</span></span> <span data-ttu-id="05964-114">接続記述子では、アドレス情報、およびアダプターに関連付けられている Oracle データベースのサービスのサービス名を指定します。</span><span class="sxs-lookup"><span data-stu-id="05964-114">The connect descriptor specifies address information and the service name of the Oracle database service associated with ADAPTER.</span></span> <span data-ttu-id="05964-115">Oracle Net Configuration Assistant を使用して、作成 tnsnames.ora で net サービス名を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="05964-115">You can use the Oracle Net Configuration Assistant to create and configure net service names in tnsnames.ora.</span></span> <span data-ttu-id="05964-116">Net サービス名を構成した後は、次の例に示す接続 URI で指定できます。</span><span class="sxs-lookup"><span data-stu-id="05964-116">After you have configured the net service name, you can specify it in a connection URI as in the following example.</span></span>  
  
```  
oracledb://ADAPTER  
```  
  
 <span data-ttu-id="05964-117">Oracle Net Configuration Assistant の使用方法と tnsnames.ora の詳細については、Oracle データベース Net Services 管理者ガイド 』 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="05964-117">For more information about using the Oracle Net Configuration Assistant and about tnsnames.ora, see the Oracle Database Net Services Administrator's Guide.</span></span> <span data-ttu-id="05964-118">特定のインストールの構成の詳細についてデータベース管理者に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="05964-118">Consult your database administrator about configuration details for your specific installation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05964-119">参照</span><span class="sxs-lookup"><span data-stu-id="05964-119">See Also</span></span>  
[<span data-ttu-id="05964-120">Oracle データベースへの接続の作成</span><span class="sxs-lookup"><span data-stu-id="05964-120">Create a connection to the Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/create-a-connection-to-the-oracle-database.md)