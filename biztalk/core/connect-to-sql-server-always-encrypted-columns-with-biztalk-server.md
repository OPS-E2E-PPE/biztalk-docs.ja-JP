---
title: BizTalk Server と SQL Server の Always Encrypted の列への接続 |Microsoft Docs
ms.custom: ''
ms.date: 11/20/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fcc20a2b-daf9-4b7f-ae61-cb408e4bd04c
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2fd02a1c89b3c308fc853dde8b541d23aa999053
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008555"
---
# <a name="connect-to-sql-server-always-encrypted-columns-with-biztalk-server"></a><span data-ttu-id="219fc-102">BizTalk Server と SQL Server の Always Encrypted の列への接続します。</span><span class="sxs-lookup"><span data-stu-id="219fc-102">Connect to SQL Server Always Encrypted columns with BizTalk Server</span></span>
<span data-ttu-id="219fc-103">WCF-SQL アダプターで Always Encrypted を有効に[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]暗号化された列を照会します。</span><span class="sxs-lookup"><span data-stu-id="219fc-103">Enable Always Encrypted in the WCF-SQL adapter in [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] to query encrypted columns.</span></span>  

<span data-ttu-id="219fc-104">**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** 、WCF-SQL アダプターは、暗号化された列をクエリできます[!INCLUDE[btsSQLServerNoVersion_md](../includes/btssqlservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="219fc-104">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]**, the WCF-SQL adapter can query encrypted columns in [!INCLUDE[btsSQLServerNoVersion_md](../includes/btssqlservernoversion-md.md)].</span></span> <span data-ttu-id="219fc-105">`ColumnEncryptionSetting`を有効にするか、Always Encrypted データベースから暗号化/復号化の列の値を取得するための機能を無効にするために使用がプロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="219fc-105">The `ColumnEncryptionSetting` binding property is used to enable or disable the functionality to get decrypted/encrypted column values from an Always Encrypted database.</span></span>

<span data-ttu-id="219fc-106">このトピックでは、有効またはこの機能を無効にする方法を示します[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="219fc-106">This topic shows you how to enable or disable this feature in [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span>

> [!TIP]
> <span data-ttu-id="219fc-107">[Always Encrypted (データベース エンジン)](https://docs.microsoft.com/sql/relational-databases/security/encryption/always-encrypted-database-engine)有用なリソースを理解し、この詳細については、[!INCLUDE[btsSQLServerNoVersion_md](../includes/btssqlservernoversion-md.md)]機能します。</span><span class="sxs-lookup"><span data-stu-id="219fc-107">[Always Encrypted (Database Engine)](https://docs.microsoft.com/sql/relational-databases/security/encryption/always-encrypted-database-engine) is a great resource to understand and learn more about this [!INCLUDE[btsSQLServerNoVersion_md](../includes/btssqlservernoversion-md.md)] feature.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="219fc-108">前提条件</span><span class="sxs-lookup"><span data-stu-id="219fc-108">Prerequisites</span></span>
<span data-ttu-id="219fc-109">インストール[Feature Pack 2](https://aka.ms/bts2016fp2)上、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="219fc-109">Install [Feature Pack 2](https://aka.ms/bts2016fp2) on your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span>

## <a name="enable-always-encrypted"></a><span data-ttu-id="219fc-110">Always Encrypted を有効にします。</span><span class="sxs-lookup"><span data-stu-id="219fc-110">Enable Always Encrypted</span></span>

1. <span data-ttu-id="219fc-111">**BizTalk Server 管理**コンソールで、WCF SQL ポートを右クリックし、選択**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="219fc-111">In the **BizTalk Server Administration** console, right-click your WCF-SQL port, and select **Properties**.</span></span>
2. <span data-ttu-id="219fc-112">移動して、**バインド**タブ。</span><span class="sxs-lookup"><span data-stu-id="219fc-112">Go to the **Binding** tab.</span></span>
3. <span data-ttu-id="219fc-113">**Always Encrypted**、有効化または無効にする、`ColumnEncryptionSettings`プロパティ。</span><span class="sxs-lookup"><span data-stu-id="219fc-113">Under **Always Encrypted**, enable or disable the `ColumnEncryptionSettings` property:</span></span>

* <span data-ttu-id="219fc-114">**有効になっている**: ポート クエリ、および Always Encrypted データベースから暗号化されたデータを取得します</span><span class="sxs-lookup"><span data-stu-id="219fc-114">**Enabled**: The port queries, and gets encrypted data from an Always Encrypted database</span></span>
* <span data-ttu-id="219fc-115">**無効になっている**: ポートは、Always Encrypted データベースをクエリできますが、返されるデータはハッシュされています</span><span class="sxs-lookup"><span data-stu-id="219fc-115">**Disabled**: The port queries the Always Encrypted database, but the data returned is hashed</span></span>

    ![Always Encrypted を有効にします。](../core/media/enable-always-encrypted.png)

4. <span data-ttu-id="219fc-117">選択**適用**、および**OK**変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="219fc-117">Select **Apply**, and **OK** to save your changes.</span></span>

## <a name="see-also"></a><span data-ttu-id="219fc-118">参照</span><span class="sxs-lookup"><span data-stu-id="219fc-118">See also</span></span>
[<span data-ttu-id="219fc-119">Always Encrypted (データベース エンジン)</span><span class="sxs-lookup"><span data-stu-id="219fc-119">Always Encrypted (Database Engine)</span></span>](https://docs.microsoft.com/sql/relational-databases/security/encryption/always-encrypted-database-engine)  
[<span data-ttu-id="219fc-120">Feature Pack を構成します。</span><span class="sxs-lookup"><span data-stu-id="219fc-120">Configure the Feature Pack</span></span>](../core/configure-the-feature-pack.md)