---
title: .NET Framework Data Provider for mySAP Business Suite の制限事項 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Data Provider for SAP, limitations of
- .NET Framework Data Provider for mySAP Business Suite, limitations of
ms.assetid: 462e627d-41da-4456-bc62-e8cf7296f5b4
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9efcf7fb18471c92c504e08df43482fbc64064d2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999819"
---
# <a name="limitations-of-the-net-framework-data-provider-for-mysap-business-suite"></a><span data-ttu-id="241fe-102">.NET Framework Data Provider for mySAP Business Suite の制限事項</span><span class="sxs-lookup"><span data-stu-id="241fe-102">Limitations of the .NET Framework Data Provider for mySAP Business Suite</span></span>
<span data-ttu-id="241fe-103">次の制限事項を呼びます、 [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] ([!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)])。</span><span class="sxs-lookup"><span data-stu-id="241fe-103">The following are known limitations of the [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] ([!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]):</span></span>  
  
- <span data-ttu-id="241fe-104">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]はセキュリティで保護されたネットワーク接続 (SNC) を使用して SAP システムへの接続をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="241fe-104">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] does not support connecting to an SAP system using Secure Network Connection (SNC).</span></span> <span data-ttu-id="241fe-105">SNC の詳細については、[SAP システムとアダプター間のセキュリティ](../../adapters-and-accelerators/adapter-sap/security-between-the-sap-system-and-the-adapter.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="241fe-105">For more information about SNC, see [Security between the SAP system and the adapter](../../adapters-and-accelerators/adapter-sap/security-between-the-sap-system-and-the-adapter.md).</span></span>
  
- <span data-ttu-id="241fe-106">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]はサポートしていません、`DbType`または`Size`のプロパティ、`SAPParameter`します。</span><span class="sxs-lookup"><span data-stu-id="241fe-106">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] does not support the `DbType` or `Size` properties of the `SAPParameter`.</span></span> <span data-ttu-id="241fe-107">代わりに、ユーザーがの値を指定すると、`SAPParameter`値を内部的に確立されている .NET と SAP のデータ型マッピングに従って .NET データ型にキャストします。</span><span class="sxs-lookup"><span data-stu-id="241fe-107">Instead, when the user specifies a value for the `SAPParameter`, the value is cast internally to a .NET data type according to the established mapping between .NET and SAP data types.</span></span>  
  
- <span data-ttu-id="241fe-108">SAP のデータ型のフィールド値の最大長`CURR`、 `DEC`、および`QUAN`は 29 桁です。</span><span class="sxs-lookup"><span data-stu-id="241fe-108">The maximum length allowed for field values of SAP data types `CURR`, `DEC`, and `QUAN` is 29 digits.</span></span> <span data-ttu-id="241fe-109">SAP では、31 の場所にこれらの値のデータ型をネイティブの .NET decimal データ型を変換先で 29 桁の制限が課せられます。</span><span class="sxs-lookup"><span data-stu-id="241fe-109">Although SAP provides 31 places for these data-type values natively, the .NET decimal data type to which they are converted imposes a 29-digit limit.</span></span>  
  
- <span data-ttu-id="241fe-110">.NET データ型間のマッピング制限`Double`と SAP`FLTP`データ型に SAP システムから .NET 型にデータを読み取るときにオーバーフロー エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="241fe-110">A mapping limitation between the .NET data type `Double` and the SAP `FLTP` data type can cause an overflow error when reading data from the SAP system into the .NET type.</span></span> <span data-ttu-id="241fe-111">.NET 型が正の 1.79769313486232 e 308 ~ SAP 負 1.79769313486232 e 308 から範囲の値を倍精度の 64 ビットの数値を表すことができますが`FLTP`で種類が解析され、 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] 1.8446744073709552E + 19; を超えることはできません有効な制限、`FLTP`型が負の 1.8446744073709552E + 正 1.8446744073709552E + 19 19 の範囲。</span><span class="sxs-lookup"><span data-stu-id="241fe-111">Although the .NET type can represent a double-precision 64-bit number with values ranging from negative 1.79769313486232e308 to positive 1.79769313486232e308, an SAP `FLTP` type parsed by the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] cannot exceed 1.8446744073709552E+19; the effective limit for the `FLTP` type is the range negative 1.8446744073709552E+19 to positive 1.8446744073709552E+19.</span></span>  
  
- <span data-ttu-id="241fe-112">基になるクライアント ライブラリで処理をタイムアウトに関する問題のため、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]コマンドと接続のタイムアウトをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="241fe-112">Due to issues with timeout handling by the underlying client library, the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] does not support command and connection timeout.</span></span>  
  
- <span data-ttu-id="241fe-113">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]非同期コマンドの動作をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="241fe-113">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] does not support asynchronous command behavior.</span></span>  
  
- <span data-ttu-id="241fe-114">SQL Server Integration Services (SSIS) プロジェクトで使用する場合、 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] 8000 以上の文字の値を含む列のデータの取得に失敗します。</span><span class="sxs-lookup"><span data-stu-id="241fe-114">When used with a SQL Server Integration Services (SSIS) project, the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] fails to retrieve data for columns that contain values with more than 8000 characters.</span></span> <span data-ttu-id="241fe-115">これに基づいて、SSIS の制限が原因です。</span><span class="sxs-lookup"><span data-stu-id="241fe-115">This is due to an SSIS restriction according to which:</span></span>  
  
  -   <span data-ttu-id="241fe-116">SSIS 変数に 4,000 文字よりも大きい値がサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="241fe-116">Values greater than 4000 characters in SSIS variable are not supported.</span></span>  
  
  -   <span data-ttu-id="241fe-117">4000 のワイド文字を超える値はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="241fe-117">Values greater than 4000 wide characters are not supported.</span></span>  
  
  -   <span data-ttu-id="241fe-118">1 バイト文字で 8000 を超える値はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="241fe-118">Values greater than 8000 single-byte characters are not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="241fe-119">参照</span><span class="sxs-lookup"><span data-stu-id="241fe-119">See Also</span></span>  
 [<span data-ttu-id="241fe-120">.NET Framework Data Provider for mySAP Business Suite について</span><span class="sxs-lookup"><span data-stu-id="241fe-120">About the .NET Framework Data Provider for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/about-the-net-framework-data-provider-for-mysap-business-suite.md)