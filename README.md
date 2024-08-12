# THE-FINALS-3.8.2-SDK

```C++
FName.ToString_Offset = 0x4156570;

uint64_t DecryptWorld()
{
    uint64_t ImageBase = (uint64_t)GetModuleHandleA(NULL);

    __m128i* unk_A179CA0 = (__m128i*)(ImageBase + 0xA179CA0);
    __m128i* unk_A179C80 = (__m128i*)(ImageBase + 0xA179C80);

    uint32_t v11 = 16777619                             
        * ((unsigned int)(16777619
            * __ROL4__(
                ((unsigned __int64)unk_A179CA0 >> 32)
                + 16777619 * __ROL4__(16777619 * __ROL4__((unsigned int)unk_A179CA0, 20) - 1427080284, 14)
                - 1427080284,
                13)
            - 1427080284) >> 8)
        - 1427080284;
    char v12 = v11 ^ BYTE2(v11);
    __m128i v13 = _mm_loadu_si128((const __m128i*)((char*)unk_A179C80 + 48 * (((unsigned __int8)v11 ^ BYTE2(v11)) & 7) + 56));
    __m128i v14 = _mm_shufflelo_epi16(_mm_or_si128(_mm_slli_epi32(v13, 0x1Au), _mm_srli_epi32(v13, 6u)), 57);
    uint64_t v15 = _mm_or_si128(_mm_slli_epi32(v14, 0xBu), _mm_srli_epi32(v14, 0x15u)).m128i_u64[0];
    __m128i v16 = _mm_loadu_si128((const __m128i*)((char*)unk_A179C80 + 48 * ((v12 + 1) & 7) + 56));
    __m128i v17 = _mm_shufflelo_epi16(_mm_or_si128(_mm_slli_epi32(v16, 0x1Au), _mm_srli_epi32(v16, 6u)), 57);
    return v15
        + (_mm_or_si128(_mm_slli_epi32(v17, 0xBu), _mm_srli_epi32(v17, 0x15u)).m128i_u64[0] ^ (0x100000001B3i64
            * __ROL8__(
                0x100000001B3i64
                * __ROL8__(v15, 55)
                + 0x626C4D24EB3E0524i64,
                31)
            + 0x626C4D24EB3E0524i64));

}

uint64_t DecryptGEngine()
{
    uint64_t ImageBase = (uint64_t)GetModuleHandleA(NULL);

    __m128i* xmmword_A175790 = (__m128i*)(ImageBase + 0xA175790);
    __m128i* xmmword_7AABCB0 = (__m128i*)(ImageBase + 0x7AABCB0);

    uint32_t v12 = 16777619
        * ((unsigned int)(16777619
            * __ROL4__(
                ((unsigned __int64)xmmword_A175790 >> 32)
                + 16777619 * __ROL4__(16777619 * __ROL4__((unsigned int)xmmword_A175790, 20) + 1475302425, 14)
                + 1475302425,
                13)
            + 1475302425) >> 8)
        + 1475302425;
    char v13 = v12 ^ BYTE2(v12);
    __int64 v14 = 3i64 * (((unsigned __int8)v12 ^ BYTE2(v12)) & 7);
    __m128i si128 = _mm_load_si128((const __m128i*) & xmmword_A175790[v14 + 2]);
    __m128i v16 = _mm_shufflelo_epi16(_mm_or_si128(_mm_slli_epi64(si128, 0xAu), _mm_srli_epi64(si128, 0x36u)), 30);
    __m128i v17 = _mm_load_si128((const __m128i*) xmmword_7AABCB0);
    uint64_t v18 = _mm_shuffle_epi8(_mm_or_si128(_mm_slli_epi32(v16, 0x1Au), _mm_srli_epi32(v16, 6u)), v17).m128i_u64[0];
    __int64 v19 = 3i64 * ((v13 + 1) & 7);
    __m128i v20 = _mm_load_si128((const __m128i*) & xmmword_A175790[v19 + 2]);
    __m128i v21 = _mm_shufflelo_epi16(_mm_or_si128(_mm_slli_epi64(v20, 0xAu), _mm_srli_epi64(v20, 0x36u)), 30);
    __int64 v22 = __ROL8__(v18, 48)
        + (__ROL8__(
            _mm_shuffle_epi8(_mm_or_si128(_mm_slli_epi32(v21, 0x1Au), _mm_srli_epi32(v21, 6u)), v17).m128i_u64[0],
            48) ^ (0x100000001B3i64 * __ROL8__(0x100000001B3i64 * __ROL8__(v18, 26) + 0x7A8F2366C4413879i64, 53)
                + 0x7A8F2366C4413879i64));
    return v22;
}

UE_UClass* UE_UObject::GetClassPrivate()
{
	__m128i xmmword_7AABC50 = *(__m128i*)(GameBase + 0x7AABC50);

	__m128i v21 = _mm_loadu_si128((const __m128i*)((char*)this + 40));
	__m128i v22 = _mm_shufflelo_epi16(_mm_or_si128(_mm_slli_epi32(v21, 0xEu), _mm_srli_epi32(v21, 0x12u)), 57);
	__m128i v23 = _mm_shuffle_epi8(_mm_or_si128(_mm_slli_epi32(v22, 2u), _mm_srli_epi32(v22, 0x1Eu)), (__m128i)xmmword_7AABC50);
	__int64* v5 = (__int64*)_mm_or_si128(_mm_slli_epi16(v23, 0xBu), _mm_srli_epi16(v23, 5u)).m128i_i64[0];
	return (UE_UClass*)v5;
}
```
