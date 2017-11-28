---
title: "BizTalk Server と SQL Server の Always Encrypted の列への接続 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fcc20a2b-daf9-4b7f-ae61-cb408e4bd04c
caps.latest.revision: "4"
author: tordgladnordahl
ms.author: tonordah
manager: anneta
ms.openlocfilehash: 62b570fabda6a0e46f87c36b863e2b99e464020b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="connect-to-sql-server-always-encrypted-columns-with-biztalk-server"></a><span data-ttu-id="7d9cc-102">BizTalk Server と SQL Server の Always Encrypted の列への接続します。</span><span class="sxs-lookup"><span data-stu-id="7d9cc-102">Connect to SQL Server Always Encrypted columns with BizTalk Server</span></span>
<span data-ttu-id="7d9cc-103">WCF-SQL アダプターで Always Encrypted が有効に[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]を暗号化された列を照会します。</span><span class="sxs-lookup"><span data-stu-id="7d9cc-103">Enable Always Encrypted in the WCF-SQL adapter in [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] to query encrypted columns.</span></span>  

<span data-ttu-id="7d9cc-104">**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** 、WCF-SQL アダプターの暗号化された列を照会できます[!INCLUDE[btsSQLServerNoVersion_md](../includes/btssqlservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="7d9cc-104">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]**, the WCF-SQL adapter can query encrypted columns in [!INCLUDE[btsSQLServerNoVersion_md](../includes/btssqlservernoversion-md.md)].</span></span> <span data-ttu-id="7d9cc-105">`ColumnEncryptionSetting`プロパティのバインドは有効にするにまたは Always Encrypted データベースから列の暗号化/暗号化解除の値を取得するための機能を無効にするのに使用します。</span><span class="sxs-lookup"><span data-stu-id="7d9cc-105">The `ColumnEncryptionSetting` binding property is used to enable or disable the functionality to get decrypted/encrypted column values from an Always Encrypted database.</span></span>

<span data-ttu-id="7d9cc-106">このトピックを有効またはこの機能を無効にする方法を示します[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="7d9cc-106">This topic shows you how to enable or disable this feature in [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span>

> [!TIP] 
> <span data-ttu-id="7d9cc-107">[Always Encrypted (データベース エンジン)](https://docs.microsoft.com/sql/relational-databases/security/encryption/always-encrypted-database-engine)を理解し、詳細については、優れたリソース[!INCLUDE[btsSQLServerNoVersion_md](../includes/btssqlservernoversion-md.md)]機能します。</span><span class="sxs-lookup"><span data-stu-id="7d9cc-107">[Always Encrypted (Database Engine)](https://docs.microsoft.com/sql/relational-databases/security/encryption/always-encrypted-database-engine) is a great resource to understand and learn more about this [!INCLUDE[btsSQLServerNoVersion_md](../includes/btssqlservernoversion-md.md)] feature.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7d9cc-108">前提条件</span><span class="sxs-lookup"><span data-stu-id="7d9cc-108">Prerequisites</span></span>
<span data-ttu-id="7d9cc-109">インストール[機能パック 1](https://www.microsoft.com/download/details.aspx?id=55100)上、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="7d9cc-109">Install [Feature Pack 1](https://www.microsoft.com/download/details.aspx?id=55100) on your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span>

## <a name="enable-always-encrypted"></a><span data-ttu-id="7d9cc-110">Always Encrypted を有効にします。</span><span class="sxs-lookup"><span data-stu-id="7d9cc-110">Enable Always Encrypted</span></span>

1. <span data-ttu-id="7d9cc-111">**BizTalk Server 管理コンソール**コンソールで、WCF SQL ポートを右クリックしを選択して**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="7d9cc-111">In the **BizTalk Server Administration** console, right-click your WCF-SQL port, and select **Properties**.</span></span>
2. <span data-ttu-id="7d9cc-112">移動して、**バインド**タブです。</span><span class="sxs-lookup"><span data-stu-id="7d9cc-112">Go to the **Binding** tab.</span></span>
3. <span data-ttu-id="7d9cc-113">**Always Encrypted**、有効化または無効にする、`ColumnEncryptionSettings`プロパティ。</span><span class="sxs-lookup"><span data-stu-id="7d9cc-113">Under **Always Encrypted**, enable or disable the `ColumnEncryptionSettings` property:</span></span>

* <span data-ttu-id="7d9cc-114">**有効になっている**: ポート クエリ、および Always Encrypted データベースから暗号化されたデータを取得</span><span class="sxs-lookup"><span data-stu-id="7d9cc-114">**Enabled**: The port queries, and gets encrypted data from an Always Encrypted database</span></span>
* <span data-ttu-id="7d9cc-115">**無効になっている**: ポートは、Always Encrypted データベースをクエリできますが、返されるデータはハッシュされています</span><span class="sxs-lookup"><span data-stu-id="7d9cc-115">**Disabled**: The port queries the Always Encrypted database, but the data returned is hashed</span></span>

    ![Always Encrypted を有効にします。](../core/media/enable-always-encrypted.png)

4. <span data-ttu-id="7d9cc-117">選択**適用**と**OK**して変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="7d9cc-117">Select **Apply**, and **OK** to save your changes.</span></span>

## <a name="see-also"></a><span data-ttu-id="7d9cc-118">参照</span><span class="sxs-lookup"><span data-stu-id="7d9cc-118">See also</span></span>
[<span data-ttu-id="7d9cc-119">Always Encrypted (Database Engine) (Always Encrypted (データベース エンジン))</span><span class="sxs-lookup"><span data-stu-id="7d9cc-119">Always Encrypted (Database Engine)</span></span>](https://docs.microsoft.com/sql/relational-databases/security/encryption/always-encrypted-database-engine)  
[<span data-ttu-id="7d9cc-120">この機能パックを構成します。</span><span class="sxs-lookup"><span data-stu-id="7d9cc-120">Configure the Feature Pack</span></span>](../core/configure-the-feature-pack.md)