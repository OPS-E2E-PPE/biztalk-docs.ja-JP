---
title: "トラブルシューティング、Adapter1 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- JD Edwards EnterpriseOne adapters, wildcard characters
- adapters [JD Edwards EnterpriseOne adapters], wildcard characters
- wildcard characters, JD Edwards EnterpriseOne adapters
ms.assetid: f5a55e52-039a-4aea-8251-b697fd061ddc
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b77b42854a58d7fe8ffafd177e91f327a7f5e7e5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshooting-the-adapter"></a><span data-ttu-id="5205d-102">アダプターのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="5205d-102">Troubleshooting the Adapter</span></span>
<span data-ttu-id="5205d-103">このトピックでは、Microsoft BizTalk Adapter for JD Edwards EnterpriseOne の使用中に発生する可能性がある問題の特定と解決に役立つ情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="5205d-103">This topic contains information to help you identify and resolve issues that you might experience while using Microsoft BizTalk Adapter for JD Edwards EnterpriseOne.</span></span>  
  
## <a name="cannot-use-wildcards-in-send-port-properties"></a><span data-ttu-id="5205d-104">送信ポートのプロパティにワイルドカードを使用できない</span><span class="sxs-lookup"><span data-stu-id="5205d-104">Cannot use wildcards in send port properties</span></span>  
 <span data-ttu-id="5205d-105">Adapter for JD Edwards Enterprise One では、以下の送信ポート プロパティ フィールドにワイルドカードを使用できません。</span><span class="sxs-lookup"><span data-stu-id="5205d-105">Adapter for JD Edwards Enterprise One does not support using wildcards in the following send port property fields:</span></span>  
  
-   <span data-ttu-id="5205d-106">[ユーザー名]</span><span class="sxs-lookup"><span data-stu-id="5205d-106">Username</span></span>  
  
-   <span data-ttu-id="5205d-107">JDE 環境</span><span class="sxs-lookup"><span data-stu-id="5205d-107">JDE Environment</span></span>  
  
-   <span data-ttu-id="5205d-108">Host</span><span class="sxs-lookup"><span data-stu-id="5205d-108">Host</span></span>  
  
-   <span data-ttu-id="5205d-109">ポート</span><span class="sxs-lookup"><span data-stu-id="5205d-109">Port</span></span>  
  
-   <span data-ttu-id="5205d-110">Java_Home</span><span class="sxs-lookup"><span data-stu-id="5205d-110">Java_Home</span></span>  
  
-   <span data-ttu-id="5205d-111">JDE JAR ファイル</span><span class="sxs-lookup"><span data-stu-id="5205d-111">JDE JAR Files</span></span>  
  
-   <span data-ttu-id="5205d-112">セキュリティ サーバー名</span><span class="sxs-lookup"><span data-stu-id="5205d-112">Security Server Name</span></span>  
  
-   <span data-ttu-id="5205d-113">サービス名接続</span><span class="sxs-lookup"><span data-stu-id="5205d-113">Service Name Connect</span></span>  
  
-   <span data-ttu-id="5205d-114">Data Source Name</span><span class="sxs-lookup"><span data-stu-id="5205d-114">Data Source Name</span></span>  
  
-   <span data-ttu-id="5205d-115">データベースの所有者</span><span class="sxs-lookup"><span data-stu-id="5205d-115">Database Owner</span></span>  
  
-   <span data-ttu-id="5205d-116">データベース サーバー名</span><span class="sxs-lookup"><span data-stu-id="5205d-116">Database Server Name</span></span>  
  
-   <span data-ttu-id="5205d-117">データベースの種類</span><span class="sxs-lookup"><span data-stu-id="5205d-117">Database Type</span></span>  
  
-   <span data-ttu-id="5205d-118">物理データベース名</span><span class="sxs-lookup"><span data-stu-id="5205d-118">Physical Database Name</span></span>  
  
## <a name="connecting-to-oracle-database"></a><span data-ttu-id="5205d-119">Oracle データベースへの接続</span><span class="sxs-lookup"><span data-stu-id="5205d-119">Connecting to Oracle database</span></span>  
 <span data-ttu-id="5205d-120">Oracle データベースを JD Edwards で使用する場合、jdeinterop.ini ファイルを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5205d-120">When using Oracle database with JD Edwards you must modify the jdeinterop.ini file.</span></span> <span data-ttu-id="5205d-121">シングル サインオンを使用する場合、[JDBj-ORACLE] セクションは Oracle の tnsnames の場所を定義します。このデータベース パラメーターを使用する必要があります。また、SQLNET.ORA ファイルが BizTalk Server コンピューター上に存在する必要があります (このファイルは Oracle Client に付属しています)。</span><span class="sxs-lookup"><span data-stu-id="5205d-121">Using Single-Sign-On the [JDBj-ORACLE] section defines Oracle tnsnames location; the database parameter must be used; and the SQLNET.ORA file must be present on the BizTalk Server computer (this should be included with the Oracle Client).</span></span>  
  
 <span data-ttu-id="5205d-122">次の内容を jdeinterop.ini ファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="5205d-122">Add the following to the jdeinterop.ini file:</span></span>  
  
1.  <span data-ttu-id="5205d-123">[JDBj-ORACLE] の下: </span><span class="sxs-lookup"><span data-stu-id="5205d-123">Under [JDBj-ORACLE]:</span></span>  
  
    ```  
    tns=c:\Oracle\ora92\network\Admin\tnsnames.ora  
    ```  
  
2.  <span data-ttu-id="5205d-124">[JDBj-BOOTSTRAP DATA SOURCE] の下: </span><span class="sxs-lookup"><span data-stu-id="5205d-124">Under [JDBj-BOOTSTRAP DATA SOURCE]:</span></span>  
  
    ```  
    database=sys810 [hardcode the database name. This information is available in the JDE.ini file on the JD Edwards computer.]  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="5205d-125">参照</span><span class="sxs-lookup"><span data-stu-id="5205d-125">See Also</span></span>  
 <span data-ttu-id="5205d-126">[JD Edwards EnterpriseOne 用送信ポートを作成する方法](../core/how-to-create-send-ports-for-jd-edwards-enterpriseone.md) </span><span class="sxs-lookup"><span data-stu-id="5205d-126">[How to Create Send Ports for JD Edwards EnterpriseOne](../core/how-to-create-send-ports-for-jd-edwards-enterpriseone.md) </span></span>  
 [<span data-ttu-id="5205d-127">JD Edwards EnterpriseOne のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="5205d-127">Troubleshooting JD Edwards EnterpriseOne</span></span>](../core/troubleshooting-jd-edwards-enterpriseone.md)