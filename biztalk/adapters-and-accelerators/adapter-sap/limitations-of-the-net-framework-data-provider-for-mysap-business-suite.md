---
title: ".NET Framework Data Provider for mySAP Business Suite の制限事項 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Data Provider for SAP, limitations of
- .NET Framework Data Provider for mySAP Business Suite, limitations of
ms.assetid: 462e627d-41da-4456-bc62-e8cf7296f5b4
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5fd4ad3a57e2b762a53582ceb77eb65f23a535fc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="limitations-of-the-net-framework-data-provider-for-mysap-business-suite"></a><span data-ttu-id="169f0-102">.NET Framework Data Provider for mySAP Business Suite の制限事項</span><span class="sxs-lookup"><span data-stu-id="169f0-102">Limitations of the .NET Framework Data Provider for mySAP Business Suite</span></span>
<span data-ttu-id="169f0-103">次はの既知の制限、 [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] ([!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)])。</span><span class="sxs-lookup"><span data-stu-id="169f0-103">The following are known limitations of the [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] ([!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]):</span></span>  
  
-   <span data-ttu-id="169f0-104">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]セキュリティで保護されたネットワーク接続 (SNC) を使用して SAP システムへの接続をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="169f0-104">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] does not support connecting to an SAP system using Secure Network Connection (SNC).</span></span> <span data-ttu-id="169f0-105">SNC の詳細については、次を参照してください。 [SAP システムとアダプター間のセキュリティ](../../adapters-and-accelerators/adapter-sap/security-between-the-sap-system-and-the-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="169f0-105">For more information about SNC, see [Security between the SAP system and the adapter](../../adapters-and-accelerators/adapter-sap/security-between-the-sap-system-and-the-adapter.md).</span></span>
  
-   <span data-ttu-id="169f0-106">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]はサポートしていません、`DbType`または`Size`のプロパティ、`SAPParameter`です。</span><span class="sxs-lookup"><span data-stu-id="169f0-106">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] does not support the `DbType` or `Size` properties of the `SAPParameter`.</span></span> <span data-ttu-id="169f0-107">代わりに、ユーザーがの値を指定すると、 `SAPParameter`.NET と SAP のデータ型の間に確立したマップに従って .NET データ型に値が内部的にキャストします。</span><span class="sxs-lookup"><span data-stu-id="169f0-107">Instead, when the user specifies a value for the `SAPParameter`, the value is cast internally to a .NET data type according to the established mapping between .NET and SAP data types.</span></span>  
  
-   <span data-ttu-id="169f0-108">SAP データ型のフィールド値の許可されている最大の長さ`CURR`、 `DEC`、および`QUAN`29 桁がします。</span><span class="sxs-lookup"><span data-stu-id="169f0-108">The maximum length allowed for field values of SAP data types `CURR`, `DEC`, and `QUAN` is 29 digits.</span></span> <span data-ttu-id="169f0-109">SAP は 31 の場所にこれらのデータ型の値ネイティブには、変換先の .NET decimal データ型に 29 桁の制限が適用されます。</span><span class="sxs-lookup"><span data-stu-id="169f0-109">Although SAP provides 31 places for these data-type values natively, the .NET decimal data type to which they are converted imposes a 29-digit limit.</span></span>  
  
-   <span data-ttu-id="169f0-110">.NET データ型間のマッピング制限`Double`と SAP`FLTP`データ型に .NET 型に SAP システムからデータを読み取るときにオーバーフロー エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="169f0-110">A mapping limitation between the .NET data type `Double` and the SAP `FLTP` data type can cause an overflow error when reading data from the SAP system into the .NET type.</span></span> <span data-ttu-id="169f0-111">.NET 型が値までの範囲-1.79769313486232e308 から 1.79769313486232 e 308、SAP と倍精度の 64 ビットの数値を表すことができますが`FLTP`によって型が解析され、 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] 1.8446744073709552E + 19 を超えることはできません効率的な制限、`FLTP`型は負の値の 1.8446744073709552E + 正 1.8446744073709552E + 19 に 19 の範囲です。</span><span class="sxs-lookup"><span data-stu-id="169f0-111">Although the .NET type can represent a double-precision 64-bit number with values ranging from negative 1.79769313486232e308 to positive 1.79769313486232e308, an SAP `FLTP` type parsed by the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] cannot exceed 1.8446744073709552E+19; the effective limit for the `FLTP` type is the range negative 1.8446744073709552E+19 to positive 1.8446744073709552E+19.</span></span>  
  
-   <span data-ttu-id="169f0-112">基になるクライアント ライブラリによるタイムアウトの処理に関する問題のため、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]コマンドと接続のタイムアウトをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="169f0-112">Due to issues with timeout handling by the underlying client library, the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] does not support command and connection timeout.</span></span>  
  
-   <span data-ttu-id="169f0-113">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]非同期コマンドの動作をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="169f0-113">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] does not support asynchronous command behavior.</span></span>  
  
-   <span data-ttu-id="169f0-114">SQL Server Integration Services (SSIS) プロジェクトで使用する場合、 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] 8000 以上の文字の値が含まれている列のデータの取得に失敗します。</span><span class="sxs-lookup"><span data-stu-id="169f0-114">When used with a SQL Server Integration Services (SSIS) project, the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] fails to retrieve data for columns that contain values with more than 8000 characters.</span></span> <span data-ttu-id="169f0-115">これに基づいて、SSIS の制限のため次に示します。</span><span class="sxs-lookup"><span data-stu-id="169f0-115">This is due to an SSIS restriction according to which:</span></span>  
  
    -   <span data-ttu-id="169f0-116">SSIS 変数内の 4,000 文字より大きい値を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="169f0-116">Values greater than 4000 characters in SSIS variable are not supported.</span></span>  
  
    -   <span data-ttu-id="169f0-117">4000 のワイド文字を超える値はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="169f0-117">Values greater than 4000 wide characters are not supported.</span></span>  
  
    -   <span data-ttu-id="169f0-118">1 バイト文字で 8000 を超える値はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="169f0-118">Values greater than 8000 single-byte characters are not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="169f0-119">参照</span><span class="sxs-lookup"><span data-stu-id="169f0-119">See Also</span></span>  
 [<span data-ttu-id="169f0-120">.NET Framework Data Provider for mySAP Business Suite</span><span class="sxs-lookup"><span data-stu-id="169f0-120">About the .NET Framework Data Provider for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/about-the-net-framework-data-provider-for-mysap-business-suite.md)