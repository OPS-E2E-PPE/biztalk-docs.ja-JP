---
title: Oracle E-business Suite アダプターのクライアントの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 842b6ecc-5334-4cc0-af10-baa7f692ad23
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 13c29eef73f5268571c9c9eb33635a0f336954f6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375670"
---
# <a name="configure-the-oracle-client-for-the-e-business-suite-adapter"></a><span data-ttu-id="8e8e5-102">Oracle E-business Suite アダプターのクライアントを構成します。</span><span class="sxs-lookup"><span data-stu-id="8e8e5-102">Configure the Oracle client for the E-Business Suite adapter</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="8e8e5-103">このトピックでは、Oracle データベースへの接続に tnsnames.ora を使用している場合にのみ該当します。</span><span class="sxs-lookup"><span data-stu-id="8e8e5-103">This topic is relevant only if you are using tnsnames.ora to connect to the Oracle database.</span></span>  
  
 <span data-ttu-id="8e8e5-104">接続を確立するために、[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]アダプターがコンピューターにインストールされている Oracle クライアントを使用して基になる Oracle データベースに接続します。</span><span class="sxs-lookup"><span data-stu-id="8e8e5-104">To establish a connection to the [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)], the adapter connects to the underlying Oracle database through the Oracle client installed on your computer.</span></span> <span data-ttu-id="8e8e5-105">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Net サービス名を渡します Oracle E-business Suite への接続を確立するために Oracle クライアントへの接続 URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="8e8e5-105">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] passes the net service name that you specify in the connection URI to the Oracle client to establish a connection to Oracle E-Business Suite.</span></span> <span data-ttu-id="8e8e5-106">Net サービス名は、Oracle クライアントを使用して、ターゲットの Oracle データベースのサービスの接続情報を取得するエイリアスです。</span><span class="sxs-lookup"><span data-stu-id="8e8e5-106">The net service name is an alias that the Oracle client uses to acquire connection information for the target Oracle database service.</span></span>  
  
 <span data-ttu-id="8e8e5-107">Oracle クライアントを使用して構成されている名前付けの方法に従って、net サービス名を解決します。</span><span class="sxs-lookup"><span data-stu-id="8e8e5-107">The Oracle client resolves the net service name according to the naming method that it is configured to use.</span></span> <span data-ttu-id="8e8e5-108">Oracle クライアントで使用される名前付け方法を構成するのに Oracle Net Configuration Assistant を使用します。</span><span class="sxs-lookup"><span data-stu-id="8e8e5-108">You use the Oracle Net Configuration Assistant to configure the naming methods to be used by the Oracle client.</span></span> <span data-ttu-id="8e8e5-109">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle E-business Suite に接続するため、ローカルの名前付けのメソッドをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="8e8e5-109">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] supports the Local Naming method for connecting to Oracle E-Business Suite.</span></span> <span data-ttu-id="8e8e5-110">このメソッドは、net サービス名を解決するのには、tnsnames.ora、ローカル ファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="8e8e5-110">This method uses a local file, tnsnames.ora, to resolve the net service name.</span></span>  
  
 <span data-ttu-id="8e8e5-111">Tnsnames.ora ファイルは、net サービス名と接続、Oracle クライアントが特定の Oracle database service (インスタンス) への接続を確立するために必要な情報が含まれている記述子を関連付けます。</span><span class="sxs-lookup"><span data-stu-id="8e8e5-111">The tnsnames.ora file associates net service names with connect descriptors that contain the information that the Oracle client needs to establish a connection to a specific Oracle database service (instance).</span></span> <span data-ttu-id="8e8e5-112">Tnsnames.ora からエントリの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="8e8e5-112">The following is a sample entry from tnsnames.ora.</span></span>  
  
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
  
 <span data-ttu-id="8e8e5-113">このエントリの例では、アダプターは、net サービス名です。</span><span class="sxs-lookup"><span data-stu-id="8e8e5-113">In this sample entry, ADAPTER is the net service name.</span></span> <span data-ttu-id="8e8e5-114">接続記述子では、アドレス情報、およびアダプターに関連付けられている Oracle データベースのサービスのサービス名を指定します。</span><span class="sxs-lookup"><span data-stu-id="8e8e5-114">The connect descriptor specifies address information and the service name of the Oracle database service associated with ADAPTER.</span></span> <span data-ttu-id="8e8e5-115">Oracle Net Configuration Assistant を使用して、作成 tnsnames.ora で net サービス名を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="8e8e5-115">You can use the Oracle Net Configuration Assistant to create and configure net service names in tnsnames.ora.</span></span> <span data-ttu-id="8e8e5-116">Net サービス名を構成した後は、次の例に示す接続 URI で指定できます。</span><span class="sxs-lookup"><span data-stu-id="8e8e5-116">After you have configured the net service name, you can specify it in a connection URI as in the following example.</span></span>  
  
```  
oracleebs://ADAPTER  
```  
  
 <span data-ttu-id="8e8e5-117">Oracle Net Configuration Assistant の使用方法と tnsnames.ora の詳細については、Oracle データベース Net Services 管理者ガイド 』 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e8e5-117">For more information about using the Oracle Net Configuration Assistant and about tnsnames.ora, see the Oracle Database Net Services Administrator's Guide.</span></span> <span data-ttu-id="8e8e5-118">特定のインストールの構成の詳細についてデータベース管理者に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="8e8e5-118">Consult your database administrator about configuration details for your specific installation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e8e5-119">参照</span><span class="sxs-lookup"><span data-stu-id="8e8e5-119">See Also</span></span>  
 [<span data-ttu-id="8e8e5-120">Oracle E-business Suite への接続を作成します。</span><span class="sxs-lookup"><span data-stu-id="8e8e5-120">Create a connection to Oracle E-Business Suite</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-connection-to-oracle-e-business-suite.md)