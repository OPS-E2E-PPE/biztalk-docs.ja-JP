---
title: JD Edwards EnterpriseOne アダプターのトラブルシューティング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f5a55e52-039a-4aea-8251-b697fd061ddc
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d6ba3fdb8789f7d258291aee05d9e7b481e905a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65306391"
---
# <a name="troubleshooting-the-adapter"></a><span data-ttu-id="1e9f1-102">アダプターのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="1e9f1-102">Troubleshooting the Adapter</span></span>
<span data-ttu-id="1e9f1-103">このトピックでには、特定し、JD Edwards EnterpriseOne の Microsoft BizTalk Adapter の使用中に発生する可能性がある問題を解決するのに役立つ情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1e9f1-103">This topic contains information to help you identify and resolve issues that you might experience while using Microsoft BizTalk Adapter for JD Edwards EnterpriseOne.</span></span>  
  
## <a name="cannot-use-wildcards-in-send-port-properties"></a><span data-ttu-id="1e9f1-104">送信ポートのプロパティでワイルドカードを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="1e9f1-104">Cannot use wildcards in send port properties</span></span>  
 <span data-ttu-id="1e9f1-105">JD Edwards Enterprise One 用のアダプターでは、次の送信ポート プロパティ フィールドにワイルドカードを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="1e9f1-105">Adapter for JD Edwards Enterprise One does not support using wildcards in the following send port property fields:</span></span>  
  
-   <span data-ttu-id="1e9f1-106">Username</span><span class="sxs-lookup"><span data-stu-id="1e9f1-106">Username</span></span>  
  
-   <span data-ttu-id="1e9f1-107">JDE 環境</span><span class="sxs-lookup"><span data-stu-id="1e9f1-107">JDE Environment</span></span>  
  
-   <span data-ttu-id="1e9f1-108">ホスト</span><span class="sxs-lookup"><span data-stu-id="1e9f1-108">Host</span></span>  
  
-   <span data-ttu-id="1e9f1-109">Port</span><span class="sxs-lookup"><span data-stu-id="1e9f1-109">Port</span></span>  
  
-   <span data-ttu-id="1e9f1-110">Java_Home</span><span class="sxs-lookup"><span data-stu-id="1e9f1-110">Java_Home</span></span>  
  
-   <span data-ttu-id="1e9f1-111">JDE JAR ファイル</span><span class="sxs-lookup"><span data-stu-id="1e9f1-111">JDE JAR Files</span></span>  
  
-   <span data-ttu-id="1e9f1-112">セキュリティ サーバー名</span><span class="sxs-lookup"><span data-stu-id="1e9f1-112">Security Server Name</span></span>  
  
-   <span data-ttu-id="1e9f1-113">サービス名接続</span><span class="sxs-lookup"><span data-stu-id="1e9f1-113">Service Name Connect</span></span>  
  
-   <span data-ttu-id="1e9f1-114">Data Source Name</span><span class="sxs-lookup"><span data-stu-id="1e9f1-114">Data Source Name</span></span>  
  
-   <span data-ttu-id="1e9f1-115">データベースの所有者</span><span class="sxs-lookup"><span data-stu-id="1e9f1-115">Database Owner</span></span>  
  
-   <span data-ttu-id="1e9f1-116">データベース サーバー名</span><span class="sxs-lookup"><span data-stu-id="1e9f1-116">Database Server Name</span></span>  
  
-   <span data-ttu-id="1e9f1-117">データベースの種類</span><span class="sxs-lookup"><span data-stu-id="1e9f1-117">Database Type</span></span>  
  
-   <span data-ttu-id="1e9f1-118">物理データベース名</span><span class="sxs-lookup"><span data-stu-id="1e9f1-118">Physical Database Name</span></span>  
  
## <a name="connecting-to-oracle-database"></a><span data-ttu-id="1e9f1-119">Oracle データベースへの接続</span><span class="sxs-lookup"><span data-stu-id="1e9f1-119">Connecting to Oracle database</span></span>  
 <span data-ttu-id="1e9f1-120">Oracle データベースを JD Edwards で使用する場合、jdeinterop.ini ファイルを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1e9f1-120">When using Oracle database with JD Edwards you must modify the jdeinterop.ini file.</span></span> <span data-ttu-id="1e9f1-121">シングル サインオンを使用する場合、[JDBj-ORACLE] セクションは Oracle の tnsnames の場所を定義します。このデータベース パラメーターを使用する必要があります。また、SQLNET.ORA ファイルが BizTalk Server コンピューター上に存在する必要があります (このファイルは Oracle Client に付属しています)。</span><span class="sxs-lookup"><span data-stu-id="1e9f1-121">Using Single-Sign-On the [JDBj-ORACLE] section defines Oracle tnsnames location; the database parameter must be used; and the SQLNET.ORA file must be present on the BizTalk Server computer (this should be included with the Oracle Client).</span></span>  
  
 <span data-ttu-id="1e9f1-122">次の内容を jdeinterop.ini ファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="1e9f1-122">Add the following to the jdeinterop.ini file:</span></span>  
  
1.  <span data-ttu-id="1e9f1-123">[JDBJ-ORACLE]: </span><span class="sxs-lookup"><span data-stu-id="1e9f1-123">Under [JDBj-ORACLE]:</span></span>  
  
    ```  
    tns=c:\Oracle\ora92\network\Admin\tnsnames.ora  
    ```  
  
2.  <span data-ttu-id="1e9f1-124">[JDBJ-BOOTSTRAP DATA SOURCE]: </span><span class="sxs-lookup"><span data-stu-id="1e9f1-124">Under [JDBj-BOOTSTRAP DATA SOURCE]:</span></span>  
  
    ```  
    database=sys810 [hardcode the database name. This information is available in the JDE.ini file on the JD Edwards computer.]  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="1e9f1-125">参照</span><span class="sxs-lookup"><span data-stu-id="1e9f1-125">See Also</span></span>  
 <span data-ttu-id="1e9f1-126">[アダプターを追加し、成果物を作成](../core/adding-biztalk-adapter-for-jd-edwards-enterpriseone.md) </span><span class="sxs-lookup"><span data-stu-id="1e9f1-126">[Add the adapter, and create the artifacts](../core/adding-biztalk-adapter-for-jd-edwards-enterpriseone.md) </span></span>  
 [<span data-ttu-id="1e9f1-127">JD Edwards EnterpriseOne のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="1e9f1-127">Troubleshooting JD Edwards EnterpriseOne</span></span>](../core/troubleshooting-jd-edwards-enterpriseone.md)